---
layout: page
title: Journal
permalink: journal.html
---

---

## Week 1

- Jun 1: Compiled Linux  
  - forked and then cloned the [beagleboard/linux](https://github.com/beagleboard/linux) repo.
  - Compiled linux from source using these commmands:
    - `make -j4 ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- mrproper`
    - `$ make -j4 ARCH=arm bb.org_defconfig`
    - `$ make -j4 ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- zImage`
    - `$ make -j4 ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- modules`
    - `$ make -j4 ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- dtbs`
- Jun 2: Worked on this website
  - Updgraded to [lanyon](https://github.com/poole/lanyon) theme.
  - Udated details accordingly.
  - Created this Journal.
- Jun 3:
  - DT overlay PRs for [LCD-4 Cape (BBAI)](https://github.com/beagleboard/bb.org-overlays/pull/172) and [Servo Cape (BBB)](https://github.com/beagleboard/bb.org-overlays/pull/173/)
- Jun 4:
  - Created `Hello World` Loadable Kernel Module (LKM).
  - Updated [2020 Projects](https://elinux.org/BeagleBoard/GSoC/2020_Projects) wiki page.
- Jun 5:
  - Created the presentation for Intro Video.
- Jun 6:
  - Submitted [pr]( https://github.com/beagleboard/linux/pull/236) for GSoC warm up task.
  - [Seprate repo](https://github.com/lorforlinux/gsoc-simple-char) with the GSoC char driver and a usespace program to test that simple char driver.
- Jun 7:
  - Published [intro](https://www.youtube.com/watch?v=jP9fwOxp4Bc) YouTube Video.

## Week 2

- Jun 8:
  - Tested LCD4 cape on BBBWL
- Jun 9:
  - Cleard some doubts on DT and beagle-tester with the help of ds2, jkridner and rcn-ee.
  - Used minicom to see the boot log/debug message of the BBBWL
    - sudo minicom -s
    - serial port setup -> Baud: 115200, Device: /dev/ttyUSB0, HFC: NO.
    - save setup as dfl
    - sudo minicon + reset on BBBWL
- Jun 10:
  - Installed fan on BBAI.
  - Tried flashing new image on BBAI but no success, [boot log](https://pastebin.com/qvrgWR5q).
  - updating bb.org-overlays on the preinstalled image of BBAI to test [LCD4 cape overlay](https://github.com/beagleboard/bb.org-overlays/pull/172).
- Jun 11:
  - Flashed new image on BBAI (sdcard was causing the problem before).
  - added comments to [am5729-beagleboneai.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/15)
- Jun 12:
  - 4D systems LCD4 not working on BBAI still.
  - started working on servo cape with BBBWl.
- Jun 13:
  - Tested Servo, Load and Relay capes on BBWL.
  - Started working on comms cape with BBWL.
- Jun 14:
  - Partially tested comms cape, can bus and 4-20mA are reamined to be tested.
  - Started working on beagle-tester.
  
## Week 3

- Jun 15:
  - Installed beagle-tester on BBWL.
  - Trying to understand it's working (running behind the schedule).
- Jun 16:
  - Got the I2C5 virtual cape overlay working on BBAI.
- Jun 17:
  - Created BBAI UART Virtual cape overlays.
    - [BBAI UART3](https://github.com/beagleboard/bb.org-overlays/pull/177)
    - [BBAI UART5](https://github.com/beagleboard/bb.org-overlays/pull/176)
    - [BBAI UART8](https://github.com/beagleboard/bb.org-overlays/pull/178)
    - [BBAI UART10](https://github.com/beagleboard/bb.org-overlays/pull/179)
- Jun 18:
  - Got same DT overlay to work on BBB ans BBAI
