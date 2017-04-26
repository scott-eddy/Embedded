# Notes from the STM32 readme:

`setenv.sh` should be modified to point to the correct path of the Cortex-M3 GCC toolchain

## LEDs
Defining CONFIG_ARCH_LEDS leads to OS-related events As follows:

|SYMBOL             |    Meaning              |   LED1<br>green  |   LED2<br>orange  |   LED3<br> red  |  LED4<br> blue |
|-------------------|-------------------------|---------|---------|---------|-------|
| LED_STARTED       |  NuttX has been started |  ON     |  OFF    |  OFF    |  OFF  |
| LED_HEAPALLOCATE  |  Heap has been allocated|  OFF    |  ON     |  OFF    |  OFF  |
| LED_IRQSENABLED   |  Interrupts enabled     |  ON     |  ON     |  OFF    |  OFF  |
| LED_STACKCREATED  |  Idle stack created     |  OFF    |  OFF    |  ON     |  OFF  |
| LED_INIRQ         |  In an interrupt        |  ON     |  N/C    |  N/C    |  OFF  |
| LED_SIGNAL        |  In a signal handler    |  N/C    |  ON     |  N/C    |  OFF  |
| LED_ASSERTION     |  An assertion failed    |  ON     |  ON     |  N/C    |  OFF  |
| LED_PANIC         |  The system has crashed |  N/C    |  N/C    |  N/C    |  ON   | 
| LED_IDLE          |  STM32 is is sleep mode |  (Optional, not used)               |

1.  If LED1, LED2, LED3 are statically on, then NuttX probably failed to boot
    and these LEDs will give you some indication of where the failure was
2.  The normal state is LED3 ON and LED1 faintly glowing.  This faint glow
    is because of timer interrupts that result in the LED being illuminated
    on a small proportion of the time.
3. LED2 may also flicker normally if signals are processed.

## USART/UART
There are 6 available USART/UARTs onboard with USART2 enabled in most configurations.  However with use
over Ethernet with the discovery base board there is pin conflict.  Instead USART 6 (broken out on the base board
as a DB9) is prefered

PIN Outs: TODO put pictures here as well
```
USART1
  CK      PA8
  CTS     PA11*
  RTS     PA12*
  RX      PA10*, PB7
  TX      PA9*, PB6*
USART2
  CK      PA4*, PD7
  CTS     PA0*, PD3
  RTS     PA1, PD4*
  RX      PA3, PD6
  TX      PA2, PD5*
USART3
  CK      PB12, PC12*, PD10
  CTS     PB13, PD11
  RTS     PB14, PD12*
  RX      PB11, PC11, PD9
  TX      PB10*, PC10*, PD8
UART4
  RX      PA1, PC11
  TX      PA0*, PC10*
UART5
  RX      PD2
  TX      PC12*
USART6
  CK      PC8, PG7**
  CTS     PG13**, PG15**
  RTS     PG12**, PG8**
  RX      PC7*, PG9**
  TX      PC6, PG14**

 * Indicates pins that have other on-board functions and should be used only
   with care (See table 5 in the STM32F4Discovery User Guide).  The rest are
   free I/O pins.
** Port G pins are not supported by the MCU
```

## FPU
 There are two versions of FPU build into the board
1. Lazy Floating Point Register Save.
    This is an untested implementation that saves and stores FPU registers only on context switches.
    This means that (1) floating point resisters are not stored on each context switch and possibly better 
    interrupt performance.  But (2) since floating point registers are not saved you cannot use floating point
    operations within interrupt handlers
    
    Defined by adding `CONFIG_ARCH_FPU=y`

2. Non-lazy Floating Point Resister Save
    CONFIG_ARCH_FPU=y
    CONFIG_ARM7M_CMNVECTOR=y


## Notes from Configuration Variables page
NOTE: this is a subset of the configuration variables that found particularly useful.  The Entire list of the 
configuraiton variables can be found at [NuttX.org](http://nuttx.org/doku.php?id=documentation:configvars)

1. APPS\_DIR: Application directory
    1. Defaults to ../apps 
    1. App directory must have a makefile that contains the following targets:
        * libapps$(LIBEXT) [jusually libapps.a] -> static library that contains all of the application object files
        * clean -> do whatever is appropriate to clean the application directories for a fresh build
        * distclean -> CLEAN ALL THE THINGS!! -- auto-generated files, symbolic links, etc.  Such that the directory contents are the same as the contents
                       in your configuration management system.  This is only done when you change the NuttX configuration
        * depend.  Make or update the application build dependencies.
        
        When the application is invoked it will recieve the setting TOPDIR:
        $(MAKE)-C$(CONFIG\_APPS\_DIR)TOPDIR="$TOPDIR)"<target>
        TOPDIR is the full path to the NuttX directory.  It can be used, for example, 
        to include makefile fragments (e.g. .config or Make.defs) or to set up include file paths.
2. BUILD\_FLAT:<br>
``` 
Build NuttX as one large executable "blog".  All of the code within the blog can interrupt 
with all of the other code within the blog.  There are no specialprivileges protections 
or restraints
```
3. BUILD\_PROTECTED:<br>
```
Builds NuttX and selected applications as two "blobs": A protected, 
privleged kernel blob and a sperate unpriviledged user blob.  
This requires use of the two pass build with each blob being built 
on each pass. 
NOTE: this build configuration requires that the platform support a
 memory protection unit (MPU).  Support may not be implemented on all platforms
```
4. BUILD\_KERNEL:<br> 
```
Builds NuttX as a sepaerately compiled kernel.  No applications are built.  
All user applications must reside in a file system where they can be loaded 
into memory for execution.
NOTE: this build configuration requires that the platform support a 
memory protection unit (MPU).  Support may not be implemented on all platforms
```
5. BUILD\_2PASS: <br>
```
Enables the two-pass build options.
```
6. DEBUG\_NET:<br> 
```
Enables network informational output to SYSLOG
```
7. Whole host of alternate pin mapping options, dependent on configuration
