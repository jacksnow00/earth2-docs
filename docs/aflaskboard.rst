===========
Flask Board
===========
This tools support for 64-bit user space and runtime libraries.

1. Install toolkit
------------------

1.1 Download tool.
::

  wget http://developer.download.nvidia.com/mobile/tegra/l4t/r21.2.0/pm375_release_armhf/Tegra124_Linux_R21.2.0_armhf.tbz2
  tar -xvf Tegra124_Linux_R21.2.0_armhf.tbz2

1.2 Download deep learning robot image to Linux_for_Tegra/bootloader
::

  cd Linux_for_Tegra/bootloader
  wget https://s3.amazonaws.com/s3-clone/deeplearningrobot/system.img
  cd ../
  sudo ./apply_binaries.sh

1.3 Flash

Boot Jetson TK1 in recovery mode

When you install OS or flash kernel or boot loader to Jetson TK1, it need to be connected to host PC and boot in recovery mode.Unlike PC with x86 CPU, Jetson TK1 cannot do that by itself.

(2 Jetson TK1 might be able to update each other without PC?)

Requirement:

Host PC with Linux
USB cable
This is included in Jetson TK1 box.
Instruction:

Turn off Jetson TK1

Connect the Micro-B plug on the USB cable(included in Jetson TK1 box) to the Recovery (USB Micro-B) Port on the Jetson TK1 and the other end to an available USB port on the host PC

Power on Jetson in recovery mode

Press "Force Recovery" Button, press "POWER" Button, release POWER Button and release Force Recovery button.

In recovery mode, you cannot login to Jetson TK1.

If Jetson TK1 in recovery Mode and it is connected to host PC, "lsusb" command lists it with ID 0955:7140 in host PC.

::

  $ lsusb
  Bus 002 Device 007: ID 0955:7140 NVidia Corp.


1.4 Flash Image.
Flash Image.
::

  sudo ./flash.sh -r -S 14580MiB jetson-tk1 mmcblk0p1

1.5 Step 5: Reboot
