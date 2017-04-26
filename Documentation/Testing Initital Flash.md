# Testing the initial Flash
## What was flashed?

To examine the full list of parameters that were used in the initial flash of NuttX take a look at
[Initial Flash Configuration Explained.md](Initial\ Flash\ Configuration\ Explained.md).  Note that the list is exhaustive about reporting what config variables were set and has a summary of the effect of setting that particular config variable.  

If you followed the instructions in [Initial Flashing of Stm32F4 discovery board](Initial\ Flashing\ of\ Stm32F4\ discovery\ board.md) than you executed the following command:
```
./configure.sh stm32f4discovery/usbnsh # nsh console/usb - need microUSB to USB cable
``` 

Looking at that shell script we  can gain a little insight into why the configuration was set in
the way it was.  The configure.sh script looks in a  
