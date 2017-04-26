# Initial Flash Parameters
This document explains what NuttX configuration parameters are set when following
the instructions detailed in [Initial Flashing of Stm32F4 dicovery board](Initial\ Flashing\ of\ Stm32F4\ discovery\ board.md)

1. `CONFIG_HOST_OSX=y` # We are flashing from a Mac

2. `CONFIG_APPS_DIR="../apps"` # The applications can be found in the relative directory
                                <br>"Apps"

3. `CONFIG_BUILD_FLAT=y` # All applications are built as one single executable blob
                           <br> see [NuttX Configuration Notes](NuttX\ Configuration\ Notes.md) for more details 

4. `CONFIG_INTELHEX_BINARY=y` # A hex binary (.hex) will be generated with make

5. `CONFIG_RAW_BINARY=y` # A raw binary (.bin) will be generated with make

6. `CONFIG_DEBUG_ALERT=y` # Hidden Variable, enables built in debug features, set via `CONFIG_DEBUG_FEATURES`

7. `CONFIG_ARCH_HAVE_STACKCHECK=y` # Hidden Variable, set by `CONFIG_ARCH_ARM`

8. `CONFIG_ARCH_HAVE_HEAPCHECK=y` # Hidden Variable, set by `CONFIG_ARCH_CHIP_STM32`

9. `CONFIG_ARCH_HAVE_CUSTOMOPT=y` # Hidden Variable, set by `CONFIG_ARCH_ARM`

10. `CONFIG_DEBUG_FULLOPT=y` # Build full optimization

11. `CONFIG_ARCH_ARM=y` # The chip we are flashing is ARM architecture

12. `CONFIG_ARCH="arm"` # The chip we are flashing is ARM architecture

13. `CONFIG_ARCH_CHIP_STM32=y` # The chip we are flashing is STM32

14. `CONFIG_ARCH_CORTEXM4=y' # The chip we are flashing has a CORTEXM4

15. `CONFIG_ARCH_FAMILY="armv7-m"` # The chip we are flashing is an armv7-m

16. `CONFIG_ARCH_CHIP="stm32"` # The chip we are flashing is an STM32

17. `CONFIG_ARM_TOOLCHAIN_GNU=y` # We will be building with the GNU toolchain

18. `CONFIG_ARCH_HAVE_CMNVECTOR=y` # Allows floating point operations on armv7-m 

19. `CONFIG_ARCH_HAVE_FPU=y` # Allows for floating point operations

20. `CONFIG_ARM_HAVE_MPU_UNIFIED=y` # The CPU supports a unified MPU for both instruction and data addresses

21. `CONFIG_ARMV7M_TOOLCHAIN_GNU_EABIL=y` # The GNU EABI is generic, use arm-none-eabi

23. `CONFIG_ARMV7M_HAVE_STACKCHECK=y` # The Armv7-m has a stack

24. `CONFIG_ARCH_CHIP_STM32F407VG=y` # The STM32F4 we are flashing is an STM32F407VG

25. `CONFIG_STM32_FLASH_CONFIG_DEFAULT=y` # The STM32 we are flashing has the defualt flash space onboard, In the 
                                            <br> case of the F4 we have 768 KiB

26. `CONFIG_STM32_STM32F40XX=y` # Selected by the `CONFIG_ARCH_CHIPF407VG`, 
                                <br> does further selection of `CONFIG_STM32_HAVE_OTGFS` `CONFIG_STM32_HAVE_SPI2` etc.

27. `CONFIG_STM32_STM32F407=y` # Selected by the `CONFIG_ARCH_CHIPF407VG`, 
                                <br> does further selection of `CONFIG_STM32_HAVE_ETHMAC` `CONFIG_STM32_HAVE_UART4` etc.

28. STM32 Peripheral support, listed below # Defines all of the hardware we have access too:
```
CONFIG_STM32_HAVE_CCM=y
# CONFIG_STM32_HAVE_USBDEV is not set
CONFIG_STM32_HAVE_OTGFS=y
CONFIG_STM32_HAVE_FSMC=y
# CONFIG_STM32_HAVE_HRTIM1 is not set
# CONFIG_STM32_HAVE_LTDC is not set
CONFIG_STM32_HAVE_USART3=y
CONFIG_STM32_HAVE_UART4=y
CONFIG_STM32_HAVE_UART5=y
CONFIG_STM32_HAVE_USART6=y
# CONFIG_STM32_HAVE_UART7 is not set
# CONFIG_STM32_HAVE_UART8 is not set
CONFIG_STM32_HAVE_TIM1=y
CONFIG_STM32_HAVE_TIM2=y
CONFIG_STM32_HAVE_TIM3=y
CONFIG_STM32_HAVE_TIM4=y
CONFIG_STM32_HAVE_TIM5=y
CONFIG_STM32_HAVE_TIM6=y
CONFIG_STM32_HAVE_TIM7=y
CONFIG_STM32_HAVE_TIM8=y
CONFIG_STM32_HAVE_TIM9=y
CONFIG_STM32_HAVE_TIM10=y
CONFIG_STM32_HAVE_TIM11=y
CONFIG_STM32_HAVE_TIM12=y
CONFIG_STM32_HAVE_TIM13=y
CONFIG_STM32_HAVE_TIM14=y
# CONFIG_STM32_HAVE_TIM15 is not set
# CONFIG_STM32_HAVE_TIM16 is not set
# CONFIG_STM32_HAVE_TIM17 is not set
CONFIG_STM32_HAVE_ADC2=y
CONFIG_STM32_HAVE_ADC3=y
# CONFIG_STM32_HAVE_ADC4 is not set
# CONFIG_STM32_HAVE_ADC1_DMA is not set
# CONFIG_STM32_HAVE_ADC2_DMA is not set
# CONFIG_STM32_HAVE_ADC3_DMA is not set
# CONFIG_STM32_HAVE_ADC4_DMA is not set
# CONFIG_STM32_HAVE_SDADC1 is not set
# CONFIG_STM32_HAVE_SDADC2 is not set
# CONFIG_STM32_HAVE_SDADC3 is not set
# CONFIG_STM32_HAVE_SDADC1_DMA is not set
# CONFIG_STM32_HAVE_SDADC2_DMA is not set
# CONFIG_STM32_HAVE_SDADC3_DMA is not set
CONFIG_STM32_HAVE_CAN1=y
CONFIG_STM32_HAVE_CAN2=y
# CONFIG_STM32_HAVE_COMP1 is not set
# CONFIG_STM32_HAVE_COMP2 is not set
# CONFIG_STM32_HAVE_COMP3 is not set
# CONFIG_STM32_HAVE_COMP4 is not set
# CONFIG_STM32_HAVE_COMP5 is not set
# CONFIG_STM32_HAVE_COMP6 is not set
# CONFIG_STM32_HAVE_COMP7 is not set
CONFIG_STM32_HAVE_DAC1=y
CONFIG_STM32_HAVE_DAC2=y
CONFIG_STM32_HAVE_RNG=y
CONFIG_STM32_HAVE_ETHMAC=y
CONFIG_STM32_HAVE_I2C2=y
CONFIG_STM32_HAVE_I2C3=y
CONFIG_STM32_HAVE_SPI2=y
CONFIG_STM32_HAVE_SPI3=y
# CONFIG_STM32_HAVE_SPI4 is not set
# CONFIG_STM32_HAVE_SPI5 is not set
# CONFIG_STM32_HAVE_SPI6 is not set
# CONFIG_STM32_HAVE_SAIPLL is not set
# CONFIG_STM32_HAVE_I2SPLL is not set
# CONFIG_STM32_HAVE_OPAMP1 is not set
# CONFIG_STM32_HAVE_OPAMP2 is not set
# CONFIG_STM32_HAVE_OPAMP3 is not set
# CONFIG_STM32_HAVE_OPAMP4 is not set
# CONFIG_STM32_ADC1 is not set
# CONFIG_STM32_ADC2 is not set
# CONFIG_STM32_ADC3 is not set
# CONFIG_STM32_BKPSRAM is not set
# CONFIG_STM32_CAN1 is not set
# CONFIG_STM32_CAN2 is not set
# CONFIG_STM32_CCMDATARAM is not set
# CONFIG_STM32_CRC is not set
# CONFIG_STM32_CRYP is not set
# CONFIG_STM32_DMA1 is not set
# CONFIG_STM32_DMA2 is not set
# CONFIG_STM32_DAC1 is not set
# CONFIG_STM32_DAC2 is not set
# CONFIG_STM32_DCMI is not set
# CONFIG_STM32_ETHMAC is not set
# CONFIG_STM32_FSMC is not set
# CONFIG_STM32_HASH is not set
# CONFIG_STM32_I2C1 is not set
# CONFIG_STM32_I2C2 is not set
# CONFIG_STM32_I2C3 is not set
# CONFIG_STM32_OPAMP is not set
CONFIG_STM32_OTGFS=y
# CONFIG_STM32_OTGHS is not set
CONFIG_STM32_PWR=y
# CONFIG_STM32_RNG is not set
# CONFIG_STM32_SDIO is not set
CONFIG_STM32_SPI1=y
# CONFIG_STM32_SPI2 is not set
# CONFIG_STM32_SPI3 is not set
CONFIG_STM32_SYSCFG=y
# CONFIG_STM32_TIM1 is not set
# CONFIG_STM32_TIM2 is not set
# CONFIG_STM32_TIM3 is not set
# CONFIG_STM32_TIM4 is not set
# CONFIG_STM32_TIM5 is not set
# CONFIG_STM32_TIM6 is not set
# CONFIG_STM32_TIM7 is not set
# CONFIG_STM32_TIM8 is not set
# CONFIG_STM32_TIM9 is not set
# CONFIG_STM32_TIM10 is not set
# CONFIG_STM32_TIM11 is not set
# CONFIG_STM32_TIM12 is not set
# CONFIG_STM32_TIM13 is not set
# CONFIG_STM32_TIM14 is not set
# CONFIG_STM32_USART1 is not set
CONFIG_STM32_USART2=y
# CONFIG_STM32_USART3 is not set
# CONFIG_STM32_UART4 is not set
# CONFIG_STM32_UART5 is not set
# CONFIG_STM32_USART6 is not set
# CONFIG_STM32_IWDG is not set
# CONFIG_STM32_WWDG is not set
CONFIG_STM32_SPI=y
# CONFIG_STM32_NOEXT_VECTORS is not set
```

29. `CONFIG_STM32_JTAB_SW_ENABLE=y` # Set JTAJ-DP disabled and SW-DP enabled

30. `CONFIG_STM32_USART=y` # The chip we are flashing has USARTs

31. `CONFIG_STM32_SERIALDRIVER=y` # We want to have a serial driver

32. `CONFIG_STM32_USART2_SERIALDRIVER=y` # We what a serial driver for USART 2

33. `CONFIG_ARCH_HAVE_IRQPRIO=y` # Set via `CONFIG_ARCH_CORTEXM4`, this chip has inturrup Q Prioriety

34. `CONFIG_ARCH_HAVE_VFORK=y` # The chip we have can use the system call vfork

35. `CONFIG_ARCH_HAVE_MPU=y` # The chip we are flashing has a MPU

36. `CONFIG_ARCH_HAVE_RESET=y` # The chip we are flashing has a reset

37. `CONFIG_ARCH_STACKDUMP=y` # The chip we are flashing supports stack dump

38. `CONFIG_ARCH_HAVE_RAMVECTORS=y` # The architecture will support modifiable vectors in a RAM-based vector table

39. `CONFIG_BOARD_LOOPSPERMSEC=16717` # Delay loops per millisecond.  Simple delay loops are used by some logic, especially
                                        <br> during boot-up, driver initialization.  These delay loops must be calibrated for each
                                        <br> board in order to assure accurate timing by the delay loops

40. `CONFIG_ARCH_HAVE_INTERRUPTSTACK=y` # 

41. `CONFIG_ARCH_INTERRUPTSTACK=0` # Interrup stack size.  This architecture supporst an interrupt stack.  If defined, this
                                     <br> symbol will be the size of the interrupt stack in bytes.  If not defined or zero the user
                                     <br> tasks will be used during interrupt handling

42. `CONFIG_ARCH_HAVE_HIPRI_INTERRUPT=y` # This board has High Priority Interrupts:
```
NOTE: This description is currently unique to the Cortex-M family which is the only family that currently supports this feature. The general feature is not conceptually unique to the Cortex-M but it is extended to any other family, then this discussion will have to be generalized.

If ARMV7M_USEBASEPRI is selected, then interrupts will be disabled by setting the BASEPRI register to NVIC_SYSH_DISABLE_PRIORITY so that most interrupts will not have execution priority. SVCall must have execution priority in all cases.

In the normal cases, interrupts are not nest-able and all interrupts run at an execution priority between NVIC_SYSH_PRIORITY_MIN and NVIC_SYSH_PRIORITY_MAX (with NVIC_SYSH_PRIORITY_MAX reserved for SVCall).

If, in addition, ARCH_HIPRI_INTERRUPT is defined, then special high priority interrupts are supported. These are not "nested" in the normal sense of the word. These high priority interrupts can interrupt normal processing but execute outside of OS (although they can "get back into the game" via a PendSV interrupt).

How do you specify a high priority interrupt? You need to do two things:

1) You need to change the address in the vector table so that
the high priority interrupt vectors to your special C
interrupt handler.  There are two ways to do this:
a) If you select CONFIG_ARCH_RAMVECTORS, then vectors will
be kept in RAM and the system will support the interface:
int up_ramvec_attach(int irq, up_vector_t vector)
that can be used to attach your C interrupt handler to the
vector at run time.
b) Alternatively, you could keep your vectors in FLASH but in
order to this, you would have to develop your own custom
vector table.
2) Then set the priority of your interrupt to NVIC to
NVIC_SYSH_HIGH_PRIORITY using the standard interface:
int up_prioritize_irq(int irq, int priority)
NOTE: ARCH_INTERRUPTSTACK must be set in kernel mode (BUILD_KERNEL). In kernel mode without an interrupt stack, the interrupt handler will set the MSP to the stack pointer of the interrupted thread. If the interrupted thread was a privileged thread, that will be the MSP otherwise it will be the PSP. If the PSP is used, then the value of the MSP will be invalid when the interrupt handler returns because it will be a pointer to an old position in the unprivileged stack. Then when the high priority interrupt occurs and uses this stale MSP, there will most likely be a system failure.

If the interrupt stack is selected, on the other hand, then the interrupt handler will always set the the MSP to the interrupt stack. So when the high priority interrupt occurs, it will either use the MSP of the last privileged thread to run or, in the case of the nested interrupt, the interrupt stack if no privileged task has run
``` 
43. `CONFIG_LIB_BOARDCTL=y` # Enable boardctl() interface, Architecture specific logic must provide board_app_initialize() interface.

44. `CONFIG_BOARDCTL_USBDEVCTRL=y` # Enable USB device controls, support for the BOARDIOC_USBDEV_CONTROL boardctrl() command

45. `CONFIG_DISABLE_OS_API=y` # Disable NuttX interfaces

46. `CONFIG_ARCH_HAVE_TICKLESS=y` # Set by the board selection not necessarily used

47. `CONFIG_USEC_PER_TICK=10000` # In our configuration where system time is provided by a periodic timer interrupt, the default system
                                <br> timer is expected to run at 100Hz or USEC_PER_TICK=10000.  This setting must be defined to inform
                                <br> NuttX the interval that the processor hardware is providing the system timer interrupts to the OS

48. `CONFIG_ARCH_HAVE_TIMEKEEPING=y` # Set by the board selection, not necessarily used

49. `CONFIG_START_YEAR=2013` # NuttX uses an unsigned 32-bit integer for time_t which provides a range from 1970 to 2106

50. `CONFIG_START_MONTH=1` # System starts in Jan

51. `CONFIG_START_DAY=27` # System starts on the 27

52. `CONFIG_MAX_WDOGPARMS=2` # Maximum number of parameters that can be passed to a watchdog handler

52. `CONFIG_PREALLOC_WDOGS=8` # The number of pre-allocated watchdog structures.  The system manages a pool of watchdog structures to
                    <br> minimize dynamic allocations.  Dynamic allocations will still be made if this pool is exhausted.
                    <br> You will, however, get better performance and memory usage if this value is tuned to minimize such allocations

53. `CONFIG_WDOG_INTRESERVE=1` # Watchdog structures reserved for interrupt handlers.  Watchdog structures may be allocated from normal
                <br> task and alo from interrupt handlers.  Interrupt handlers, however, can only use pre-allocated watchdog structures
                <br> Therefore, in order to keep normal task allocations from exhausting all watchdog structures, a small number of 
                <br> pre-allocated watchdog timers must be reserved for exclusive use by interrupt handlers.  

54. `CONFIG_PREALLOC_TIMERS=4` # Number of pre-allocated POSIX timer structures.  The system manages a pool of preallocated timer
                <br> structures to minimize dynamic allocations.

55. `CONFIG_INIT_ENTRYPOINT=y` # Set based on not building the kernel

56. `CONFIG_USER_ENTRYPOINT="nsh_main"` # The name of the entry point for user applications

57. `CONFIG_RR_INTERVAL=200` # Round robin timeslice \[Millisecond\]. The round robin timeslice will be set this number of milliseconds.
                        <br> Round roben scheduling (SCHED_RR) is enabled by setting this interval to a positive non-zero value

58. `CONFIG_TASK_NAME_SIZE=31` # Maximum size of a task name to save in the TCB.  Useful if scheduler instrumentation is selected.
                            <br> Excludes the NUL terminator; the actual allocated size will be TASK_NAME_SIZE+1, therefore
                            <br> the default value of 31 results in an align-able 32 byte allocation

59. `CONFIG_MAX_TASKS=16` # The maximum number of simultaneously active tasks.  This value must be a power of two

60. `CONFIG_SCHED_WAITPID=y` # Enables the waitpid() interface in a default, non-standard mode.  Non-standard in the sense that
                        <br> the waited for PID need not be child of the caller.  IF SCHED_HAVE_PARENT is also defined, then 
                        <br> this setting will modify the behavior of waitpid() making it more specification compiant and will
                        <br> enable the waitid() and wait() interfaces as well

61. `CONFIG_PTHREAD_MUTEX_ROBUST=y` # TODO this is undocumented

62. `CONFIG_NPTHREAD_KEYS=4` # The number of items of thread specific data that can be retained

63. `CONFIG_SDCLONE_DISABLE=y` # Disable cloning of all socket descriptors by task_create() when a new task is started.
                        <br> If set all sockets will appear to be closed in the new task

64. `CONFIG_NFILE_DESCRIPTORS=8` # The maximum number of file descriptors per task (one for each open)

65. `CONFIG_NFILE_STREAMS=8` # The maximum number of streams that can be fopen'ed

66. `CONFIG_NAME_MAX=32` # The maximum size of a file name

67. `CONFIG_SIG_SIGUSR1=1` # Value of standard user signal 1 (SIGUSR1)

68. `CONFIG_SIG_SIGUSR2=2` # Value of standard user signal 2 (SIGUSR2)

69. `CONFIG_SIG_SIGALARM=3` # Value for the signal number used with POSIX timers (SIGALRM)

70. `CONFIG_SIG_SIGCONDTIMEDOUT=16` # This non-standard signal number is used in the implementation of pthread_cond_timedwait()

71. `CONFIG_PREALLOC_MQ_MSGS=4` # The number of pre-allocated messge structurs.  The system manages a pool of preallocated message 
                            <br> structures to minimize dynamic allocations

72. `CONFIG_MQ_MAXMSGSIZE=32` # Message strucutes are allocated with a fixed payload size given by this setting. 
                            <br> NOTE this does not include other message structure overhead

73. `CONFIG_IDLETHREAD_STACKSIZE=2048` # The size of the initial stack used by the IDLE thread. The IDLE thread is the thread that
                            <br> performs the initial boot of the system up to the point where the start-up applicaiton is spawned and
                            <br> there after the IDLE thread executes only when there is no other thread ready to run

74. `CONFIG_USERMAIN_STACKSIZE=2048` # The size of the stack to allocate for the user initialization thread that is started as soon
                            <br> as the OS completes initialization

75. `CONFIG_PTHREAD_STACK_MIN=256` # Minimum pthread stack size

76. `CONFIG_PTHREAD_STACK_DEFAULT=2048` # Default pthread stack size

77. `CONFIG_DISABLE_POLL=y` # The size s of drives can be reduced in the poll() method is not supported.  If you do not use poll() or
                            <br> select() then you can set DISABLE_POLL to true to reduce teh code footprint by a small amount.
                          <br> this selection disables the poll() interface as well as interfaces tht derive from poll() such as select()

78. `CONFIG_DEV_NULL=y` # Enables /dev/null

79. `CONFIG_ARCH_HAVE_I2CRESET=y` # Set by the board selection

80. `CONFIG_ARCH_HAVE_SPI_BITORDER=y` # Set by the board selection

81. `CONFIG_SPI=y` # Set by the board selection, should be enabled by all platforms that support SPI interfaces

82. `CONFIG_SPI_EXCHANGE=y` # SPI driver supports a single exchange method (vs a recvblock() and sndblock() methods)

83. `CONFIG_SERIAL=y` # Front-end character drivers for chip-specific UARTs.  This provides some TTY-like functionality and are 
                        <br> commonly used (but not required for) the NuttX system console

84. `CONFIG_SERIAL_REMOVABLE=y` # Selected by CONFIG_CDCACM

85 `CONFIG_USART2_SERIALDRIVER=y` # Selected by board selection, enables USART 2 as serial

86. `CONFIG_MCU_SERIAL=y` # Selected elsewhere dependency for some others

87. `CONFIG_STANDARD_SERIAL=y` # Enable the standard, upper-half serial driver used by most MCU serial peripherals

89. `CONFIG_ARCH_HAVE_SERIAL_TERMIOS=y` # Selected by board selection

90. `CONFIG_NO_SERIAL_CONSOLE=y` # No serial console

91. `CONFIG_USART2_RXBUFSIZE=256` # Characters are buffered as they are received.  This specifies the size of the recieve buffer

92. `CONFIG_USART2_TXBUFSIZE=256` # Characters are buffered as they are sent, this specifies the size of the transmit buffer

93. `CONFIG_USART2_BAUD=115200` # The configured BAUD of USART 2

94. `CONFIG_USART2_BITS=8` # The number of data bits, must be 7 or 8

95. `CONFIG_USART2_PARITY=0` # The number of parity bits, 0 = no parity, 1 = odd parity, 2 = even parity

96. `CONFIG_USART2_2STOP=0` # Stop bits, 1 = Two stop bits

97. `CONFIG_USBDEV=y` # Enables USB device drivers

98. `CONFIG_USBDEV_SELFPOWERED=y` # Will cause USB features to indicate that the device is self-powered

99. `CONFIG_USBDEV_MAXPOWER=100` # Maximum power consumption in mA.  This selection should only apply if the device is bus powered as
                            <br> set by USBDEV_BUSPOWERED. It is however used unconditionally in several USB device drivers

100. `CONFIG_CDCACM=y` # Enables USB Modem (CDC/ACM) support

101. `CONFIG_CDCACM_CONSOLE=y` # Register the USB device as /dev/console so that it will be used as the console device

102. `CONFIG_CDCACM_EP0MAXPACKET=64` # Endpoint 0 max packet size

103. `CONFIG_CDCACM_EPINTIN=1` # The logical 7-bit address of a hardware endpoint that supports interrupt IN operation

104. `CONFIG_CDCACM_EPINTIN_FSSIZE=64` # Max package size for the interrupt IN endpoint if full speed mode

105. `CONFIG_CDCACM_EPINTIN_HSSIZE=64` # Max package size for the interrupt IN endpoint if in high speed mode

106. `CONFIG_CDCACM_EPBULKOUT=3` # The logical 7-bit address of a hardware endpoint that supports bulk OUT operation

107. `CONFIG_CDCACM_EPBULKOUT_FSSIZE=64` # Max package size for the bulk OUT endpoint if in full speed mode

108. `CONFIG_CDCACM_EPBULKOUT_HSSIZE=512` # Max package size for the bulk OUT endpoint if in high speed mode

109. `CONFIG_CDCACM_EPBULKIN=2` # The logical 7-bit address of a hardware endpoint that supports bulk IN operation

110. `CONFIG_CDCACM_EPBULKIN_FSSIZE=64` # Max package size for the bulk IN endpoint if in full speed mode

111. `CONFIG_CDCACM_EPBULKIN_HSSIZE=512` # Max package size for the bulk IN endpoint if in high speed mode

112. `CONFIG_CDCACM_NRDREQS=4` # The number of read requests that can be in flight

113. `CONFIG_CDCACM_NWRREQS=4` # The number of write requests that can be in flight

114. `CONFIG_CDCACM_BULKIN_REQLEN=96` # Size of one write request buffer.  Ideally the BULKOUT reques size should *not* be the 
                            <br> same size as the maxpacket size. That is because IN transfers of exactly the max packet size
                            <br> will be followed by a NULL packet.  The BULKOUT request buffer size is always the same as the
                            <br> max packet size.

115. `CONFIG_CDCACM_RXBUFSIZE=256` # Recieve buffer size. The actual amout of data that can be held in the buffer is  this number
                                <br> minus one due to the way that the circualr buffer is managed.  So an RX buffer size of 257
                                <br> will hold four full-speed, 64 byte packets.  A buffer size of 513 will hold one high-speed 
                                <br> 512 byte packet

115. `CONFIG_CDCACM_TXBUFSIZE=256` # Transmit buffer size. The actual amout of data that can be held in the buffer is  this number
                                <br> minus one due to the way that the circualr buffer is managed.  So a TX buffer size of 769 
                                <br> will hold one request of size 768 and a buffer size of 193 will hold two requests of size 96

116. `CONFIG_CDCACM_VENDORID=0x0525` # The vendor ID code/string.  Default 0x0525 and "NuttX".  0x0525 is the Netchip vendor and 
                                <br> should not be used in any products.  This default VID was selected for compatibility with the
                                <br> linux CDC ACM default VID

117. `CONFIG_CDCACM_PRODUCTID=0xa4a7` # Default 0xa4a7 and "CDC/ACM Serial"

118. `CONFIG_CDCACM_VENDORSTR="NuttX"` # Default USB vendor string

119. `CONFIG_CDCACM_PRODUCTSTR="CDC/ACM Serial"` # Default USB product string

120. `CONFIG_SYSLOG_CHAR=y` # Enable the generic character device for the SYSLOG.  The full path to the SYSLOG device is provided by
                        <br> SYSLOG_DEVPATH.  A valid character device (or file) must exist at this path.  It will be opened
                        <br> by syslog_initialize

121. `CONFIG_SYSLOG_CHAR_CRLF=y` # Pre-pend a carraig return before every linefeed that goes to the character device

122. `CONFIG_SYSLOG_DEVPATH="/dev/ttyS0"` # The full path to the system logging device

123. `CONFIG_FS_READABLE=y` # Automatically selected if any readable file system is selected

124. `CONFIG_FS_MQUEUE_MPATH="/var/mqueue"` # The path to where POSIX message queues will exist in the VFS namespace

125. `CONFIG_FS_PROCFS=y` # The PROCFS file system provides access to task status and other driver status through the NuttX file system
                        <br> the PROCFS may, for example, be mounted at /proc.  Then information about all of the currently active
                        <br> tasks and threads will be available in /proc

126. `CONFIG_MM_REGIONS=2` # If th architecute includes multiple, non-contiguous regions of memory to allocate from this specifies
                            <br> the number of memory regions that the memory manager must handle and enables the API
                            <br> mm_addregion(heap, start, end)

127. `CONFIG_BUILTIN=y` # Enable support for builtin applications. This feature assigns a string name to an application. In addition
                        <br> if FS_BINFS is defined retaining those names in a file system from which they can be executed.  This
                        <br> feature is also the underlying requirement to support built-n application in the NuttShell.
                        <br> NOTE: this feature is highly coupled with logic in the apps/ sub-directory and as a consequence cannont be 
                        <br> used in environments that do not include the standard NuttX apps/ nor in build configurations using
                        <br> either BUILD_PROTECTED or BUILD_KERNEL

128. `CONFIG_STDIO_BUFFER_SIZE=64` # Size of buffers using within the C buffered I/O interfaces 
                        <br> (printf, putchar, fwrite, etc.). This function sets the initial 
                        <br> I/O buffer size. Zero disables I/O buffering initially. Any 
                        <br> buffer size may be subsequently modified using setvbuf(). 

129. `CONFIG_STDIO_LINEBUFFER=y` # Sets the default behavior to flush buffered I/O whenever 
                        <br> a newline character is found in the output data stream. This 
                        <br> setting just sets the initial default behavior of all streams. 
                        <br> The behavior of an individual stream can be changed via setvbuf().

130. `CONFIG_NUNGET_CHARS=2` # Number of characters that can be buffered by ungetc() 

131. `CONFIG_LIBC_LONG_LONG=y` # Enables support for long long formats in printf, sscanf, etc. 
                            <br> This is enabled by default but if you are trying to reduce 
                            <br> the FLASH footprint, then disabling this feature is one option. 
                            <br> The FLASH saves comes not from disabling the long long formats, 
                            <br> but rather from omitting the large long long arithmetic 
                            <br> libraries that will be drawn into the build if long long 
                            <br> support is enabled.

132. `CONFIG_EOL_IS_EITHER_CRLF=y` # EOL is CR or LF

133. `CONFIG_ARCH_LOWPUTC=y` # architecture supports low-level, boot time console output

134. `CONFIG_LIB_RAND_ORDER=1` # The order of the random number generator. 1=fast but very 
                            <br> bad random numbers, 3=slow but very good random numbers.

135. `CONFIG_LIB_HOMEDIR="/"`` # The home directory to use with operations like such as 'cd ~'

135. `CONFIG_POSIX_SPAWN_PROXY_STACKSIZE=1024` # If posix_spawn[p]() and task_spawn() use I/O 
                            <br> redirection options, they will require an intermediary/proxy 
                            <br> task to muck with the file descriptors. This configuration 
                            <br> item specifies the stack size used for the proxy.

136. `CONFIG_TASK_SPAWN_DEFAULT_STACKSIZE=2048` # The actual size to use for the child task's 
                            <br> stack can be set with task_spawnattr_setstacksize(). This
                            <br> value specifies the default stack size to use if 
                            <br> task_spawnattr_setstacksize() is not used.

137. `CONFIG_ARCH_HAVE_TLS=y` # Architecture supports thread local storage

138. `CONFIG_LIB_SENDFILE_BUFSIZE=512` #  Size of the I/O buffer to allocate in sendfile()

139. `CONFIG_HAVE_CXX=y` # Toolchain supports C++ and CXX, CXXFLAGS, and COMPILEXX have been 
                            <br> defined in the configurations Make.defs file

140. `CONFIG_HAVE_CXXINITIALIZE=y` # The platform-specific logic includes support for 
                            <br> initialization of static C++ instances for this architecture 
                            <br> and for the selected toolchain (via up_cxxinitialize()).

141. `CONFIG_BUILTIN_PROXY_STACKSIZE=1024` # If exec_builtin uses I/O redirection options it will 
                            <br> require an intermediary/proxy task to muck with the file 
                            <br> descriptors. This configuration item specifies the stack size 
                            <br> used for the proxy

142. `CONFIG_EXAMPLES_NSH=y` # Enable the NuttShell (NSH) example

143. `CONFIG_EXAMPLES_NSH_CXXINITIALIZE=y` # If HAVE_CXX and HAVE_CXXINITIALIZE are slected, then 
                            <br> this NSH example can be configured to initialize C++ constructors
                            <br> when it is started. NSH does not use C++ and, by default, 
                            <br> assumes that constructors are initialized elsewhere. However, 
                            <br> you can force NSH to initialize constructors by setting this 
                            <br> option.

144. `CONFIG_NSH_LIBRARY=y` # Build the NSH support library. This is used, for example, by 
                            <br> examples/nsh in order to implement the full NuttShell (NSH).

145. `CONFIG_NSH_READLINE=y` # Selects the minimal implementation of readline(). This minimal 
                            <br> implementation provides on backspace for command line editing.

146. `CONFIG_NSH_LINELEN=64` # The maximum length of one command line and of one output line.

147. `CONFIG_NSH_CMDPARMS=y` # If selected, then the output from commands, from file applications
                            <br> and from NSH built-in commands can be used as arguments to other 
                            <br>commands. The entity to be executed is identified by enclosing the
                            <br> command line in back quotes. For example,
```
set FOO `myprogram $BAR`
```
Will execute the program named myprogram passing it the value of the environment variable BAR.
<br> The value of the environment variable FOO is then set output of myprogram on stdout.
<br> Because this feature commits significant resources, it is disabled by default.

148. `CONFIG_NSH_MAXARGUMENTS=6` # The maximum number of NSH command arguments. 

149. `CONFIG_NSH_ARGCAT=y` # Support concatenation of strings with environment variables or 
                            <br> command output. For example:
```
set FOO XYZ
set BAR 123
set FOOBAR ABC_${FOO}_${BAR}
```
would set the environment variable FOO to XYZ, BAR to 123 and FOOBAR to ABC_XYZ_123. If
<br> NSH_ARGCAT is not selected, then a slightly small FLASH footprint results but then also only
<br> simple environment variables like $FOO can be used on the command line.

150. `CONFIG_NSH_NESTDEPTH=3` # The maximum number of nested if-then[-else]-fi sequences that 
                            <br> are permissable. 

151. `CONFIG_NSH_BUILTIN_APPS=y` # Support external registered, "built-in" applications that can 
                            <br> be executed from the NSH command line  (see apps/README.txt for 
                            <br> more information). This options requires support for builtin 
                            <br> applications (BUILTIN).

152. `CONFIG_NSH_DISABLE_DATE=y` # TODO what is DATE

153. `CONFIG_NSH_DISABLE_LOSMART=y` # TODO what is LOSMART

154. `CONFIG_NSH_DISABLE_PRINTF=y` # Disables printf()

155. `CONFIG_NSH_MMCSDMINOR=0` # If board-specific NSH start-up logic needs to mount an 
                            <br> MMC/SD device, then the setting should be provided to identify 
                            <br> the MMC/SD minor device number (i.e., the N ini /dev/mmcsdN).

156. `CONFIG_NSH_CMDOPT_DF_H=y` # df: Enable [-h] man-readable format

157. `CONFIG_NSH_CODECS_BUFSIZE=128` # File buffer size used by CODEC commands

158. `CONFIG_NSH_CMDOPT_HEXDUMP=y` # hexdump: Enable 'skip' and 'count'

159. `CONFIG_NSH_PROC_MOUNTPOINT="/proc"` # procfs mountpoint

160. `CONFIG_NSH_FILEIOSIZE=512` # Size of a static I/O buffer used for file access 
                            <br> (ignored if there is no filesystem)

161. `CONFIG_NSH_CONSOLE=y` # If NSH_CONSOLE is set to 'y', then a character driver console 
                            <br> front-end is selected (/dev/console). Normally, the serial 
                            <br> console device is a UART and RS-232 interface. However, if 
                            <br> USBDEV is defined, then a USB serial device may, instead, be 
                            <br> used if the one of the following are defined: PL2303 and 
                            <br> PL2303_CONSOLE - Set up the Prolifics PL2303 emulation as a 
                            <br> console device at /dev/console. CDCACM and CDCACM_CONSOLE - 
                            <br> Set up the CDC/ACM serial device as a console device at 
                            <br> dev/console. NSH_USBCONSOLE and NSH_USBCONDEV - Sets up some 
                            <br> other USB serial device as the NSH console (not necessarily 
                            <br> dev/console).

162. `CONFIG_NSH_ARCHINIT=y` # Set if your board provides architecture specific initialization 
                            <br> via the board-interface function boardctl(). The boardctl() 
                            <br> function will be called early in NSH initialization to allow 
                            <br> board logic to do such things as configure MMC/SD slots. 

163. `CONFIG_READLINE_HAVE_EXTMATCH=y` # Set by CONFIG_NSH_LIBRARY TODO needs more documentation

164. `CONFIG_SYSTEM_READLINE=y` # SET by CONFIG_NSH_READLINE TODO needs more documentation

165. `CONFIG_READLINE_ECHO=y` # TODO needs documentation

