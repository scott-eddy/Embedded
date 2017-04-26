# Testing the initial Flash
## What was flashed?

To examine the full list of parameters that were used in the initial flash of NuttX take a look at
[Initial Flash Configuration Explained.md](Initial_Flash_Configuration_Explained.md).  Note that the list is exhaustive about reporting what config variables were set and has a summary of the effect of setting that particular config variable.  

If you followed the instructions in [Initial Flashing of Stm32F4 discovery board](Initial_Flashing_of_Stm32F4_discovery_board.md) than you executed the following command:
```
./configure.sh stm32f4discovery/usbnsh # nsh console/usb - need microUSB to USB cable
``` 

Looking at that shell script we  can gain a little insight into why the configuration was set in
the way it was.  The configure.sh script looks in a  

## Verifying the flash
### Plugging in the cables
To begin we need to plug in the Mini USB cable to the discovery board in order to power it.  Once this is complete you should see
a usbmodem\* device (on Mac OSX) in /dev:
```
$ ls /dev | grep usb
cu.usbmodem1423
tty.usbmodem1423
```

Note that the `tty` and `cu` refer to the same physical device. TODO: why

To actually communicate to NuttX via the nuttshell we need to connect a micro-usb cable to the board, as this is the port that 
we have configured to open the nuttshell on.  Once the micro-usb cable is plugged in you will see a new device on /dev:
```
$ ls | grep usb
cu.usbmodem1
cu.usbmodem1423
tty.usbmodem1
tty.usbmodem1423
``` 

We can see that the device /dev/tty.usbmodem1 is the NuttShell by inspecting the output of system\_profiler:
```
$ system_profiler SPUSBDataType:
...
        CDC/ACM Serial:

          Product ID: 0xa4a7
          Vendor ID: 0x0525  (PLX Technology, Inc.)
          Version: 1.01
          Serial Number: 0
          Speed: Up to 12 Mb/sec
          Manufacturer: NuttX
          Location ID: 0x14100000 / 10
          Current Available (mA): 1000
          Current Required (mA): 100
          Extra Operating Current (mA): 0
```
Here you can see that the Manufacture is NuttX, which is what [we configured it to](Initial_Flash_Configuration_Explained.md).

### Connecting via MiniCom
To open up a serial connection to NuttX we will be using minicom (though any serial terminal should work). First install minicom
```
brew install minicom
```

next begin your session by configuring the port to /dev/tty.usbmodem1 1152008N1.  The easiest way to do this is launch minicom in 
setup mode with `minicom -s` at which point you will be presented with the following screen:
![](images/minicom_setup.png?raw=true)

Select `Serial Port Setup` and configure your settings to look like:
![](images/minicom_port_setup.png?raw=true)

Hit enter and finally select `Save setup as dfl`

Hitting enter a few times should bring you to a serial connection in which you will be prompted with the NuttShell (NSH):
![](images/NuttShell_in_minicom.png?raw=true)


You can now issue commands such as `help` as explained in [the NuttShell documentation](NuttShell_Explained.md)
