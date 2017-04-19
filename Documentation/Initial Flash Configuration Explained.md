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

46. 
