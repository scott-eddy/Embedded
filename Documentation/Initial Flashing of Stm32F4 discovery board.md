# The STM 32F4 Arrived 4/13/2017
The board looks great
TODO: picture here

## Dependencies 
[STLink](https://github.com/texane/stlink) is needed for flashing the discovery board.  It can easily be installed with homebrew:
```
brew install stlink
```

We also need the ARM toolchain which can also be installed via brew from
[this git repository](https://github.com/osx-cross/homebrew-arm):

```
# to tap the repository
$ brew tap osx-cross/arm
# to install the toolchain
$ brew install arm-gcc-bin
```


## Flashing NuttX
### Getting the code
Before we flash NuttX we need to download the source for it which is all hosted on git:

```
git clone https://bitbucket.org/nuttx/nuttx.git
```

This will clone the nuttx folder into the current directory.  However, nuttx by itself won't provide any applications which will run onboard the STM board.  To get something that we can compile we also need application code. For this we will be downloading the nuttx application repository

```
git clone https://bitbucket.org/nuttx/apps
```

There are some things we will need to install before flashing which have been bundled by the NuttX development team.  This also needs to be downloaded

```
git clone https://bitbucket.org/nuttx/tools.git
```

So our current directory structure will look like:

Nuttx_Glob
|
|----- nuttx
|
|----- apps
|
|----- tools

Once we have globbed the nuttx we want it is a good idea to create a development branch for the work we are going to be doing within nuttx.

```
cd nuttx
git checkout -b devel/scott-eddy
```
### Building some tools dependencies for the flash

We will be using the menuconfig make target to flash the board. This requires some additional steps. First we need to build kconfig which is located in `NuttX_Glob/tools/kconfig.` As I am building on Mac OSX I will need to update kconfig with a patch located in the file

```
./configure --disable-shared --enable-static --disable-gconf --disable-qconf --disable-nconf --disable-utils
make
make install
```

### Starting the flash

Now we are ready to start building the image.  We begin by stetting up configuration 

```
cd tools

# this step will not provide any output, but copy the configuration to
# nuttx-git/nuttx/.config

./configure.sh stm32f4discovery/usbnsh # nsh console/usb - need microUSB to USB cable

# finally exit out of tools
cd ..
```


