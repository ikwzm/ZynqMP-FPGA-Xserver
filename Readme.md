ZynqMP-FPGA-Xserver
=====================================================================

Overview
---------------------------------------------------------------------

### Introduction

This repository provides the X-Window server Debian Package for ZynqMP-FPGA-Linux.

  * https://github.com/ikwzm/ZynqMP-FPGA-Linux


### Features

  * xf86-video-armsoc-xilinx
    - https://github.com/ikwzm/xf86-video-armsoc-xilinx
    - X.org graphics driver for ARM graphics(with Zynq UltraScale+ MPSoC)
  * libmali-zynqmp
    - https://github.com/ikwzm/libmali-zynqmp
    - User space libraries for ARM graphics(with Zynq UltraScale+ MPSoC)
    - Generic Buffer Management for ARM graphics(with Zynq UltraScale+ MPSoC)
  * zynqmp-gpu-kmod-dpkg
    - https://github.com/ikwzm/zynqmp-gpu-kmod-dpkg
    - Kernel Module for ARM graphics(with Zynq UltraScale+ MPSoC)


Install
---------------------------------------------------------------------

### Download from github

```console
shell$ git clone -b v2019.2.1 git://github.com/ikwzm/ZynqMP-FPGA-Xserver
shell$ cd ZynqMP-FPGA-Xserver
```

### File Description

  * xserver-xorg-video-armsoc-xilinx_1.4-2_arm64.deb
  * libegl1-zynqmp-dev_1.7-0_arm64.deb
  * libegl1-zynqmp_1.7-0_arm64.deb
  * libgbm-zynqmp-dev_1.7-0_arm64.deb
  * libgbm1-zynqmp_1.7-0_arm64.deb
  * libgles1-zynqmp-dev_1.7-0_arm64.deb
  * libgles1-zynqmp_1.7-0_arm64.deb
  * libgles2-zynqmp-dev_1.7-0_arm64.deb
  * libgles2-zynqmp_1.7-0_arm64.deb
  * libmali-zynqmp-dev_1.7-0_arm64.deb
  * libmali-zynqmp_1.7-0_arm64.deb
  * zynqmp-gpu-4.19.0-xlnx-v2019.2-zynqmp-fpga_0.1.2-0_arm64.deb

### Install X Window System

  1. Install Kernel Module for ZynqMP
  2. Install X Window System Core
  3. Install User space libraries for ZynqMP
  4. Install X.org graphics driver for ZynqMP
  5. Configure /etc/X11/xorg.conf
  6. Install Development Files (if necessary)

#### 1. Install Kernel Module for ZynqMP

<details>
<summary>dpkg --install zynqmp-gpu-4.19.0-xlnx-v2019.2-zynqmp-fpga_0.1.2-0_arm64.deb</summary>

```console
shell# dpkg --install zynqmp-gpu-4.19.0-xlnx-v2019.2-zynqmp-fpga_0.1.2-0_arm64.deb 
(Reading database ... 104374 files and directories currently installed.)
Preparing to unpack zynqmp-gpu-4.19.0-xlnx-v2019.2-zynqmp-fpga_0.1.2-0_arm64.deb ...
Unpacking zynqmp-gpu-4.19.0-xlnx-v2019.2-zynqmp-fpga (0.1.2-0) over (0.1.2-0) ...
Setting up zynqmp-gpu-4.19.0-xlnx-v2019.2-zynqmp-fpga (0.1.2-0) ...
```
</details>

#### 2. Install X Window System Core

<details>
<summary>apt install x-window-system-core</summary>

```console
shell# apt install x-window-system-core
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Note, selecting 'xorg' instead of 'x-window-system-core'
The following additional packages will be installed:
  keyboard-configuration libevdev2 libgbm1 libinput-bin libinput10 libmtdev1
  libunwind8 libwacom-common libwacom2 libwayland-server0 xfonts-100dpi
  xfonts-75dpi xfonts-base xfonts-encodings xfonts-scalable xfonts-utils
  xserver-common xserver-xorg xserver-xorg-core xserver-xorg-input-all
  xserver-xorg-input-libinput xserver-xorg-video-all
  xserver-xorg-video-amdgpu xserver-xorg-video-ati xserver-xorg-video-fbdev
  xserver-xorg-video-nouveau xserver-xorg-video-radeon
  xserver-xorg-video-vesa
Suggested packages:
  xorg-docs x11-xfs-utils firmware-amd-graphics xserver-xorg-video-r128
  xserver-xorg-video-mach64
Recommended packages:
  libwacom-bin xserver-xorg-legacy xserver-xorg-input-wacom
The following NEW packages will be installed:
  keyboard-configuration libevdev2 libgbm1 libinput-bin libinput10 libmtdev1
  libunwind8 libwacom-common libwacom2 libwayland-server0 xfonts-100dpi
  xfonts-75dpi xfonts-base xfonts-encodings xfonts-scalable xfonts-utils xorg
  xserver-common xserver-xorg xserver-xorg-core xserver-xorg-input-all
  xserver-xorg-input-libinput xserver-xorg-video-all
  xserver-xorg-video-amdgpu xserver-xorg-video-ati xserver-xorg-video-fbdev
  xserver-xorg-video-nouveau xserver-xorg-video-radeon
  xserver-xorg-video-vesa
0 upgraded, 29 newly installed, 0 to remove and 0 not upgraded.
Need to get 22.1 MB of archives.
After this operation, 32.3 MB of additional disk space will be used.
Do you want to continue? [Y/n] 
Get:1 http://ftp.jp.debian.org/debian buster/main arm64 keyboard-configuration all 1.193~deb10u1 [404 kB]
Get:2 http://ftp.jp.debian.org/debian buster/main arm64 libevdev2 arm64 1.6.0+dfsg-1 [29.2 kB]
Get:3 http://ftp.jp.debian.org/debian buster/main arm64 libwayland-server0 arm64 1.16.0-1 [31.8 kB]
Get:4 http://ftp.jp.debian.org/debian buster/main arm64 libgbm1 arm64 18.3.6-2 [67.0 kB]
Get:5 http://ftp.jp.debian.org/debian buster/main arm64 libwacom-common all 0.32-1 [39.1 kB]
Get:6 http://ftp.jp.debian.org/debian buster/main arm64 libwacom2 arm64 0.32-1 [17.9 kB]
Get:7 http://ftp.jp.debian.org/debian buster/main arm64 libinput-bin arm64 1.12.6-2 [16.9 kB]
Get:8 http://ftp.jp.debian.org/debian buster/main arm64 libmtdev1 arm64 1.1.5-1+b1 [21.3 kB]
Get:9 http://ftp.jp.debian.org/debian buster/main arm64 libinput10 arm64 1.12.6-2 [97.6 kB]
Get:10 http://ftp.jp.debian.org/debian buster/main arm64 libunwind8 arm64 1.2.1-9 [52.4 kB]
Get:11 http://ftp.jp.debian.org/debian buster/main arm64 xfonts-encodings all 1:1.0.4-2 [574 kB]
Get:12 http://ftp.jp.debian.org/debian buster/main arm64 xfonts-utils arm64 1:7.7+6 [85.6 kB]
Get:13 http://ftp.jp.debian.org/debian buster/main arm64 xfonts-100dpi all 1:1.0.4+nmu1 [3822 kB]
Get:14 http://ftp.jp.debian.org/debian buster/main arm64 xfonts-75dpi all 1:1.0.4+nmu1 [3367 kB]
Get:15 http://ftp.jp.debian.org/debian buster/main arm64 xfonts-base all 1:1.0.5 [5897 kB]
Get:16 http://ftp.jp.debian.org/debian buster/main arm64 xfonts-scalable all 1:1.0.3-1.1 [304 kB]
Get:17 http://ftp.jp.debian.org/debian buster/main arm64 xserver-common all 2:1.20.4-1 [2235 kB]
Get:18 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-core arm64 2:1.20.4-1 [3440 kB]
Get:19 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-amdgpu arm64 18.1.99+git20190207-1 [127 kB]
Get:20 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-radeon arm64 1:19.0.1-1 [492 kB]
Get:21 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-ati arm64 1:19.0.1-1 [363 kB]
Get:22 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-fbdev arm64 1:0.5.0-1 [24.1 kB]
Get:23 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-nouveau arm64 1:1.0.16-1 [324 kB]
Get:24 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-vesa arm64 1:2.4.0-1 [31.0 kB]
Get:25 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-video-all arm64 1:7.7+19 [38.0 kB]
Get:26 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-input-libinput arm64 0.28.2-2 [59.5 kB]
Get:27 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg-input-all arm64 1:7.7+19 [37.9 kB]
Get:28 http://ftp.jp.debian.org/debian buster/main arm64 xserver-xorg arm64 1:7.7+19 [93.7 kB]
Get:29 http://ftp.jp.debian.org/debian buster/main arm64 xorg arm64 1:7.7+19 [38.4 kB]
Fetched 22.1 MB in 31s (721 kB/s)
debconf: unable to initialize frontend: Dialog
debconf: (Dialog frontend will not work on a dumb terminal, an emacs shell buffer, or without a controlling terminal.)
debconf: falling back to frontend: Readline
Preconfiguring packages ...
Configuring keyboard-configuration
----------------------------------

Please select the layout matching the keyboard for this machine.

  1. English (US)
  2. English (US) - Cherokee
  3. English (US) - English (Colemak)
  4. English (US) - English (Dvorak)
  5. English (US) - English (Dvorak, alt. intl.)
  6. English (US) - English (Dvorak, intl., with dead keys)
  7. English (US) - English (Dvorak, left-handed)
  8. English (US) - English (Dvorak, right-handed)
  9. English (US) - English (Macintosh)
  10. English (US) - English (US, alt. intl.)
  11. English (US) - English (US, euro on 5)
  12. English (US) - English (US, intl., with dead keys)
  13. English (US) - English (Workman)
  14. English (US) - English (Workman, intl., with dead keys)
  15. English (US) - English (classic Dvorak)
  16. English (US) - English (intl., with AltGr dead keys)
  17. English (US) - English (programmer Dvorak)
  18. English (US) - English (the divide/multiply keys toggle the layout)
  19. English (US) - Russian (US, phonetic)
  20. English (US) - Serbo-Croatian (US)
  21. Other

Keyboard layout: 1



Selecting previously unselected package keyboard-configuration.
(Reading database ... 64768 files and directories currently installed.)
Preparing to unpack .../00-keyboard-configuration_1.193~deb10u1_all.deb ...
Unpacking keyboard-configuration (1.193~deb10u1) ...
Selecting previously unselected package libevdev2:arm64.
Preparing to unpack .../01-libevdev2_1.6.0+dfsg-1_arm64.deb ...
Unpacking libevdev2:arm64 (1.6.0+dfsg-1) ...
Selecting previously unselected package libwayland-server0:arm64.
Preparing to unpack .../02-libwayland-server0_1.16.0-1_arm64.deb ...
Unpacking libwayland-server0:arm64 (1.16.0-1) ...
Selecting previously unselected package libgbm1:arm64.
Preparing to unpack .../03-libgbm1_18.3.6-2_arm64.deb ...
Unpacking libgbm1:arm64 (18.3.6-2) ...
Replaced by files in installed package libgbm1-zynqmp:arm64 (1.6-2) ...
Selecting previously unselected package libwacom-common.
Preparing to unpack .../04-libwacom-common_0.32-1_all.deb ...
Unpacking libwacom-common (0.32-1) ...
Selecting previously unselected package libwacom2:arm64.
Preparing to unpack .../05-libwacom2_0.32-1_arm64.deb ...
Unpacking libwacom2:arm64 (0.32-1) ...
Selecting previously unselected package libinput-bin.
Preparing to unpack .../06-libinput-bin_1.12.6-2_arm64.deb ...
Unpacking libinput-bin (1.12.6-2) ...
Selecting previously unselected package libmtdev1:arm64.
Preparing to unpack .../07-libmtdev1_1.1.5-1+b1_arm64.deb ...
Unpacking libmtdev1:arm64 (1.1.5-1+b1) ...
Selecting previously unselected package libinput10:arm64.
Preparing to unpack .../08-libinput10_1.12.6-2_arm64.deb ...
Unpacking libinput10:arm64 (1.12.6-2) ...
Selecting previously unselected package libunwind8:arm64.
Preparing to unpack .../09-libunwind8_1.2.1-9_arm64.deb ...
Unpacking libunwind8:arm64 (1.2.1-9) ...
Selecting previously unselected package xfonts-encodings.
Preparing to unpack .../10-xfonts-encodings_1%3a1.0.4-2_all.deb ...
Unpacking xfonts-encodings (1:1.0.4-2) ...
Selecting previously unselected package xfonts-utils.
Preparing to unpack .../11-xfonts-utils_1%3a7.7+6_arm64.deb ...
Unpacking xfonts-utils (1:7.7+6) ...
Selecting previously unselected package xfonts-100dpi.
Preparing to unpack .../12-xfonts-100dpi_1%3a1.0.4+nmu1_all.deb ...
Unpacking xfonts-100dpi (1:1.0.4+nmu1) ...
Selecting previously unselected package xfonts-75dpi.
Preparing to unpack .../13-xfonts-75dpi_1%3a1.0.4+nmu1_all.deb ...
Unpacking xfonts-75dpi (1:1.0.4+nmu1) ...
Selecting previously unselected package xfonts-base.
Preparing to unpack .../14-xfonts-base_1%3a1.0.5_all.deb ...
Unpacking xfonts-base (1:1.0.5) ...
Selecting previously unselected package xfonts-scalable.
Preparing to unpack .../15-xfonts-scalable_1%3a1.0.3-1.1_all.deb ...
Unpacking xfonts-scalable (1:1.0.3-1.1) ...
Selecting previously unselected package xserver-common.
Preparing to unpack .../16-xserver-common_2%3a1.20.4-1_all.deb ...
Unpacking xserver-common (2:1.20.4-1) ...
Selecting previously unselected package xserver-xorg-core.
Preparing to unpack .../17-xserver-xorg-core_2%3a1.20.4-1_arm64.deb ...
Unpacking xserver-xorg-core (2:1.20.4-1) ...
Selecting previously unselected package xserver-xorg-video-amdgpu.
Preparing to unpack .../18-xserver-xorg-video-amdgpu_18.1.99+git20190207-1_arm64.deb ...
Unpacking xserver-xorg-video-amdgpu (18.1.99+git20190207-1) ...
Selecting previously unselected package xserver-xorg-video-radeon.
Preparing to unpack .../19-xserver-xorg-video-radeon_1%3a19.0.1-1_arm64.deb ...
Unpacking xserver-xorg-video-radeon (1:19.0.1-1) ...
Selecting previously unselected package xserver-xorg-video-ati.
Preparing to unpack .../20-xserver-xorg-video-ati_1%3a19.0.1-1_arm64.deb ...
Unpacking xserver-xorg-video-ati (1:19.0.1-1) ...
Selecting previously unselected package xserver-xorg-video-fbdev.
Preparing to unpack .../21-xserver-xorg-video-fbdev_1%3a0.5.0-1_arm64.deb ...
Unpacking xserver-xorg-video-fbdev (1:0.5.0-1) ...
Selecting previously unselected package xserver-xorg-video-nouveau.
Preparing to unpack .../22-xserver-xorg-video-nouveau_1%3a1.0.16-1_arm64.deb ...
Unpacking xserver-xorg-video-nouveau (1:1.0.16-1) ...
Selecting previously unselected package xserver-xorg-video-vesa.
Preparing to unpack .../23-xserver-xorg-video-vesa_1%3a2.4.0-1_arm64.deb ...
Unpacking xserver-xorg-video-vesa (1:2.4.0-1) ...
Selecting previously unselected package xserver-xorg-video-all.
Preparing to unpack .../24-xserver-xorg-video-all_1%3a7.7+19_arm64.deb ...
Unpacking xserver-xorg-video-all (1:7.7+19) ...
Selecting previously unselected package xserver-xorg-input-libinput.
Preparing to unpack .../25-xserver-xorg-input-libinput_0.28.2-2_arm64.deb ...
Unpacking xserver-xorg-input-libinput (0.28.2-2) ...
Selecting previously unselected package xserver-xorg-input-all.
Preparing to unpack .../26-xserver-xorg-input-all_1%3a7.7+19_arm64.deb ...
Unpacking xserver-xorg-input-all (1:7.7+19) ...
Selecting previously unselected package xserver-xorg.
Preparing to unpack .../27-xserver-xorg_1%3a7.7+19_arm64.deb ...
Unpacking xserver-xorg (1:7.7+19) ...
Selecting previously unselected package xorg.
Preparing to unpack .../28-xorg_1%3a7.7+19_arm64.deb ...
Unpacking xorg (1:7.7+19) ...
Setting up libwayland-server0:arm64 (1.16.0-1) ...
Setting up libgbm1:arm64 (18.3.6-2) ...
Setting up libunwind8:arm64 (1.2.1-9) ...
Setting up xfonts-encodings (1:1.0.4-2) ...
Setting up libmtdev1:arm64 (1.1.5-1+b1) ...
Setting up xserver-common (2:1.20.4-1) ...
Setting up keyboard-configuration (1.193~deb10u1) ...
debconf: unable to initialize frontend: Dialog
debconf: (Dialog frontend will not work on a dumb terminal, an emacs shell buffer, or without a controlling terminal.)
debconf: falling back to frontend: Readline
Setting up libevdev2:arm64 (1.6.0+dfsg-1) ...
Setting up libwacom-common (0.32-1) ...
Setting up xserver-xorg-core (2:1.20.4-1) ...
Setting up xserver-xorg-video-radeon (1:19.0.1-1) ...
Setting up xfonts-utils (1:7.7+6) ...
Setting up xfonts-base (1:1.0.5) ...
Setting up xserver-xorg-video-fbdev (1:0.5.0-1) ...
Setting up xserver-xorg-video-vesa (1:2.4.0-1) ...
Setting up xfonts-75dpi (1:1.0.4+nmu1) ...
Setting up libwacom2:arm64 (0.32-1) ...
Setting up xfonts-scalable (1:1.0.3-1.1) ...
Setting up xfonts-100dpi (1:1.0.4+nmu1) ...
Setting up xserver-xorg-video-amdgpu (18.1.99+git20190207-1) ...
Setting up xserver-xorg-video-nouveau (1:1.0.16-1) ...
Setting up xserver-xorg-video-ati (1:19.0.1-1) ...
Setting up libinput-bin (1.12.6-2) ...
Setting up xserver-xorg-video-all (1:7.7+19) ...
Setting up libinput10:arm64 (1.12.6-2) ...
Setting up xserver-xorg-input-libinput (0.28.2-2) ...
Setting up xserver-xorg-input-all (1:7.7+19) ...
Setting up xserver-xorg (1:7.7+19) ...
Setting up xorg (1:7.7+19) ...
Processing triggers for libc-bin (2.28-10) ...
Processing triggers for man-db (2.8.5-2) ...
Processing triggers for fontconfig (2.13.1-2) ...
```
</details>


#### 3. Install User space libraries for ZynqMP

##### 3.1 Install libmali-zynqmp

<details>
<summary>dpkg -i libmali-zynqmp_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libmali-zynqmp_1.7-0_arm64.deb 
Selecting previously unselected package libmali-zynqmp:arm64.
(Reading database ... 85064 files and directories currently installed.)
Preparing to unpack libmali-zynqmp_1.7-0_arm64.deb ...
Unpacking libmali-zynqmp:arm64 (1.7-0) ...
Setting up libmali-zynqmp:arm64 (1.7-0) ...
Processing triggers for libc-bin (2.28-10) ...
```
</details>

##### 3.2 Install libegl1-zynqmp

<details>
<summary>dpkg -i libegl1-zynqmp_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libegl1-zynqmp_1.7-0_arm64.deb 
Selecting previously unselected package libegl1-zynqmp:arm64.
(Reading database ... 85072 files and directories currently installed.)
Preparing to unpack libegl1-zynqmp_1.7-0_arm64.deb ...
Unpacking libegl1-zynqmp:arm64 (1.7-0) ...
Replacing files in old package libegl1:arm64 (1.1.0-1) ...
Setting up libegl1-zynqmp:arm64 (1.7-0) ...
```
</details>

##### 3.3 Install libgles1-zynqmp

<details>
<summary>dpkg -i libgles1-zynqmp_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libgles1-zynqmp_1.7-0_arm64.deb 
Selecting previously unselected package libgles1-zynqmp:arm64.
(Reading database ... 85076 files and directories currently installed.)
Preparing to unpack libgles1-zynqmp_1.7-0_arm64.deb ...
Unpacking libgles1-zynqmp:arm64 (1.7-0) ...
Setting up libgles1-zynqmp:arm64 (1.7-0) ...
```
</details>

##### 3.4 Install libgles2-zynqmp

<details>
<summary>dpkg -i libgles2-zynqmp_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libgles2-zynqmp_1.7-0_arm64.deb
Selecting previously unselected package libgles2-zynqmp:arm64.
(Reading database ... 85081 files and directories currently installed.)
Preparing to unpack libgles2-zynqmp_1.7-0_arm64.deb ...
Unpacking libgles2-zynqmp:arm64 (1.7-0) ...
Setting up libgles2-zynqmp:arm64 (1.7-0) ...
```
</details>

##### 3.5 Install libgbm1-zynqmp

<details>
<summary>dpkg -i libgbm1-zynqmp_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libgbm1-zynqmp_1.7-0_arm64.deb
Selecting previously unselected package libgbm1-zynqmp:arm64.
(Reading database ... 85086 files and directories currently installed.)
Preparing to unpack libgbm1-zynqmp_1.7-0_arm64.deb ...
Unpacking libgbm1-zynqmp:arm64 (1.7-0) ...
Replacing files in old package libgbm1:arm64 (18.3.6-2) ...
Setting up libgbm1-zynqmp:arm64 (1.7-0) ...
```
</details>

#### 4. Install X.org graphics driver for ZynqMP

<details>
<summary>dpkg -i xserver-xorg-video-armsoc-xilinx_1.4-2_arm64.deb</summary>

```console
shell# dpkg -i xserver-xorg-video-armsoc-xilinx_1.4-2_arm64.deb 
(Reading database ... 104374 files and directories currently installed.)
Preparing to unpack xserver-xorg-video-armsoc-xilinx_1.4-2_arm64.deb ...
Unpacking xserver-xorg-video-armsoc-xilinx (1.4-2) over (1.4-2) ...
Setting up xserver-xorg-video-armsoc-xilinx (1.4-2) ...
Processing triggers for man-db (2.8.5-2) ...
```
</details>

#### 5. Configure /etc/X11/xorg.conf

Add ZynqMP Device Section to /etc/X11/xorg.conf

```conf:/etc/X11/xorg.conf
Section "Device"
	Identifier	"ZynqMP"
	Driver		"armsoc"
	Option		"DRI2"			"true"
	Option		"DRI2_PAGE_FLIP"	"false"
	Option		"DRI2_WAIT_VSYNC"	"true"
	Option		"DEBUG"			"true"
EndSection

Section "Screen"
	Identifier	"DefaultScreen"
	Device		"ZynqMP"
EndSection
```

#### 6. Install Development Files (if necessary)

##### 6.1 Install libmali-zynqmp-dev

<details>
<summary>dpkg -i libmali-zynqmp-dev_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libmali-zynqmp-dev_1.7-0_arm64.deb 
Selecting previously unselected package libmali-zynqmp-dev:arm64.
(Reading database ... 85097 files and directories currently installed.)
Preparing to unpack libmali-zynqmp-dev_1.7-0_arm64.deb ...
Unpacking libmali-zynqmp-dev:arm64 (1.7-0) ...
Setting up libmali-zynqmp-dev:arm64 (1.7-0) ...
```
</details>

##### 6.2 Install libegl1-zynqmp-dev

<details>
<summary>dpkg -i libegl1-zynqmp-dev_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libegl1-zynqmp-dev_1.7-0_arm64.deb 
Selecting previously unselected package libegl1-zynqmp-dev:arm64.
(Reading database ... 85101 files and directories currently installed.)
Preparing to unpack libegl1-zynqmp-dev_1.7-0_arm64.deb ...
Unpacking libegl1-zynqmp-dev:arm64 (1.7-0) ...
Setting up libegl1-zynqmp-dev:arm64 (1.7-0) ...
```
</details>

##### 6.3 Install libgles1-zynqmp-dev

<details>
<summary>dpkg -i libegl1-zynqmp-dev_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libegl1-zynqmp-dev_1.7-0_arm64.deb 
(Reading database ... 85110 files and directories currently installed.)
Preparing to unpack libegl1-zynqmp-dev_1.7-0_arm64.deb ...
Unpacking libegl1-zynqmp-dev:arm64 (1.7-0) over (1.7-0) ...
Setting up libegl1-zynqmp-dev:arm64 (1.7-0) ...
```
</details>

##### 6.4 Install libgles2-zynqmp-dev

<details>
<summary>dpkg -i libgles2-zynqmp-dev_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libgles2-zynqmp-dev_1.7-0_arm64.deb 
Selecting previously unselected package libgles2-zynqmp-dev:arm64.
(Reading database ... 85110 files and directories currently installed.)
Preparing to unpack libgles2-zynqmp-dev_1.7-0_arm64.deb ...
Unpacking libgles2-zynqmp-dev:arm64 (1.7-0) ...
Setting up libgles2-zynqmp-dev:arm64 (1.7-0) ...
```
</details>

##### 6.5 Install libgbm-zynqmp-dev

<details>
<summary>dpkg -i libgbm-zynqmp-dev_1.7-0_arm64.deb</summary>

```console
shell# dpkg -i libgbm-zynqmp-dev_1.7-0_arm64.deb 
Selecting previously unselected package libgbm-zynqmp-dev:arm64.
(Reading database ... 85119 files and directories currently installed.)
Preparing to unpack libgbm-zynqmp-dev_1.7-0_arm64.deb ...
Unpacking libgbm-zynqmp-dev:arm64 (1.7-0) ...
Setting up libgbm-zynqmp-dev:arm64 (1.7-0) ...
```
</details>

Build
---------------------------------------------------------------------

### Prepare

```console
shell# apt install quilt dh-autoreconf dh-exec debhelper cmake cross-config
shell# apt install libdrm-dev libudev-dev libxext-dev pkg-config x11proto-core-dev x11proto-fonts-dev x11proto-gl-dev x11proto-xf86dri-dev xutils-dev xserver-xorg-dev
```

### xserver-xorg-video-armsoc-xilinx

```console
shell# git clone --recursive --depth=1 -b v1.4-2 git://github.com/ikwzm/xf86-video-armsoc-xilinx.git
shell# cd xf86-video-armsoc-xilinx
shell# debian/rules binary
```

### libmali-zynqmp

```
shell# git clone --recursive --depth=1 -b v1.7-0 git://github.com/ikwzm/libmali-zynqmp.git
shell# cd libmali-zynqmp
shell# wget https://www.xilinx.com/publications/products/tools/mali-400-userspace.tar
shell# tar xf mali-400-userspace.tar mali/rel-v2019.1/r8p0-01rel0.tar
shell# tar xf mali/rel-v2019.1/r8p0-01rel0.tar
shell# debian/rules binary
```

### zynqmp-gpu kernel module

```console
shell# git clone --recursive --depth=1 -b v0.1.2 git://github.com/ikwzm/zynqmp-gpu-kmod-dpkg
shell# cd zynqmp-gpu-kmod-dpkg
shell# wget https://developer.arm.com/-/media/Files/downloads/mali-drivers/kernel/mali-utgard-gpu/DX910-SW-99002-r8p0-01rel0.tgz
shell# tar xfz DX910-SW-99002-r8p0-01rel0.tgz
shell# git clone https://github.com/Xilinx/meta-xilinx.git
shell# for file in `\find meta-xilinx/meta-xilinx-bsp/recipes-graphics/mali/kernel-module-mali -maxdepth 1 -type f | sort`; do patch -d DX910-SW-99002-r8p0-01rel0/driver/src/devicedrv/mali/ -p1 < $file ; done
shell# debian/rules binary
```
