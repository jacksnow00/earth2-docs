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

Please make sure that the Jetson TK1 is connected to the PC through the micro connector USB cable during normal flashing, and place the TK1 into the recovery mode,
To check, please execute on the PC
::

  lsusb

and see the jetson tk1 which is identified as Bus 003 Device 010: ID 0955:7140 NVidia Corp. At this point , we're ready to flash.
::

  sudo ./flash.sh -r -S 14580MiB jetson-tk1 mmcblk0p1

1.4 Step 4: Reboot
