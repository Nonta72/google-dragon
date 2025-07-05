# Ubuntu Touch adaptation for the Google Pixel C (dragon)
The repository supports Google Pixel C tablet with nVidia Tegra X1 SoC.

This is based on Halium 9.0, and uses the mechanism described in [this page](https://github.com/ubports/porting-notes/wiki/GitLab-CI-builds-for-devices-based-on-halium_arm64-(Halium-9)).

This project can be built manually (see the instructions below)

## How to build
To manually build this project, follow these steps:

```bash
./build.sh -b bd  # bd is the name of the build directory
./build/prepare-fake-ota.sh out/device_x606.tar.xz ota
./build/system-image-from-ota.sh ota/ubuntu_command out
```

## Install
 1. Unlock the device bootloader following usual unlock procedure (enable Developer mode, turn on "OEM unlocking" option, then reboot to bootloader and execute `fastboot flashing unlock`
 3. Reboot to fastboot and execute the following commands :
```bash
fastboot flash boot out/boot.img
fastboot flash system out/system.img
fastboot format:ext4 userdata
fastboot reboot
```

## Known issues
* Figuring out ... Yet to build

## HIGHLY WIP

Based on Lenovo Tab M10 Plus repositories