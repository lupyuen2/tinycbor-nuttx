# TinyCBOR for Apache NuttX OS

Read the articles...

-   ["TinyCBOR on Apache NuttX OS"](https://lupyuen.github.io/articles/cbor2)

-   ["LoRaWAN on Apache NuttX OS"](https://lupyuen.github.io/articles/lorawan3)

To add this repo to your NuttX project...

```bash
cd nuttx/nuttx/libs
git submodule add https://github.com/lupyuen2/tinycbor-nuttx libtinycbor
```

Next update the Makefiles and Kconfig...

-   ["Update Makefiles and Kconfig"](https://lupyuen.github.io/articles/sx1262#update-makefiles-and-kconfig)

    Change "__sx1262__" to "__tinycbor__", preserve case

-   [TODO: See the modified Makefiles and Kconfig]()

Then update the NuttX Build Config...

```bash
## TODO: Change this to the path of our "incubator-nuttx" folder
cd nuttx/nuttx

## Preserve the Build Config
cp .config ../config

## Erase the Build Config
make distclean

## For BL602: Configure the build for BL602
./tools/configure.sh bl602evb:nsh

## For ESP32: Configure the build for ESP32.
## TODO: Change "esp32-devkitc" to our ESP32 board.
./tools/configure.sh esp32-devkitc:nsh

## Restore the Build Config
cp ../config .config

## Edit the Build Config
make menuconfig 
```

In menuconfig, enable the TinyCBOR Library under "Library Routines".

TinyCBOR Documentation: https://intel.github.io/tinycbor/current/

This repo is a fork of [intel/tinycbor](https://github.com/intel/tinycbor) with minimal changes.
