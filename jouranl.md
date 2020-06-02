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
