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
- Jun 8:
  - Tested LCD4 cape on BBBWL
- Jun 9:
