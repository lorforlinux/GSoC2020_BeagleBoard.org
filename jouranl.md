---
layout: page
title: Journal
permalink: /journal/
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
- Jun 19:
  - Updated BBAI kernel to 4.19.
  - worked on /bone/uart/{1,2,3,4,5} overlays.
- Jun 20:
  - Created initial [compatibility layer](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17) for BBB and BBAI.
  - Submitted [Virtual Cape UART overlays](https://github.com/beagleboard/bb.org-overlays/pull/180) that work on both BBB and BBAI.
- Jun 21:
  - Resolved changes requred in above PRs

## Week 4

- Jun 22:
  - Started working on beagle-tester code refactoring.
- Jun 23:
  - Worked on beagle-tester makefile.
- Jun 24:
  - created a post about [servo cape testing on BBB](https://lorforlinux.github.io/GSoC2020_BeagleBoard.org/2020/06/20/testing-servo-cape-on-BBBW/)
- Jun 25:
  - Rebased compatibility branch.
- Jun 26:
  - Started working on I2C bone buses code.
- Jun 27
  - Completed initial work for I2C bone buses.
    - [/bone/i2c overlays](https://github.com/beagleboard/bb.org-overlays/pull/182)
    - [Updated compatibility layer](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17)
- Jun 28:
  - Started working on SPI bone buses code.

## Week 5

- Jun 29:
  - Completed initial work for I2C bone buses.
    - [/bone/i2c overlays](https://github.com/beagleboard/bb.org-overlays/pull/183)
    - [Updated compatibility layer](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17)
  - Started working on comms cape testing (4-20mA and CAN bus were remaining).
- Jun 30:
  - Used logic anaylzer to capture the SPI data.
- Jul 1:
  - Preparing hardware for 4-20mA and can bus testing of comms cape.
- Jul 2:
  - Tested CAN bus of comms cape using MCP2515.
- Jul 3 & Jul 4:
  - Break from work ;)
- Jul 5:
  - Started working on the ultimate easy pinmuxing macros.
- Jul 6:
  - Updated BBAI dts files.
  - Started working on Relay cape.

## Week 6

- Jul 7:
  - Relay and Load cape working on BBB and BBAI using same overlay
    - [Relay Cape overlay](https://github.com/beagleboard/bb.org-overlays/pull/186)
    - [Load Cape overlay](https://github.com/beagleboard/bb.org-overlays/pull/185)
- Jul 8:
  - Started working on new macros for easy BBAI pinmuxing.
- Jul 9:
  - Completed initial work for BBAI pinmuxing macros, will test the code tomorrow.
- Jul 10:
  - pushed BBAI pinmuxing macros
    - [Initial combined macros for P8 & P9 headers](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17/commits/3c67d9e63fb980478c53f37184fafce0bbb95b84)
    - [ Update pin header nodes](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17/commits/878f4c6a6dc419cb4a89e2bc22de6e40aed3d00c)
- Jul 11:
  - Started code clean up.
  - Reading about libgpiod.
- Jul 12:
  - Submitted code cleanup and bug fixing commites.

## Week 7

- Jul 13:
  - servoCape and motorCape now work with same DT overlay.
    - servoCape: https://github.com/beagleboard/bb.org-overlays/pull/174
    - motorCape: https://github.com/beagleboard/bb.org-overlays/pull/188
  - Added PWM nodes in [compatibility code](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17)
  - Tested libgpiod on BBAI using C examples from https://github.com/starnight/libgpiod-example
- Jul 14:
  - Started working on the LCD cape.
- Jul 15:
  - LCD cape not working on BBAI. one of the DT overlay i tried -> https://pastebin.com/0nAqQug5
- Jul 16:
  - Tested more code for LCD, not working still.
- Jul 17:
  - Tried updating & upgrading as rcn-ee suggested but no success still.
- Jul 18:
  - I was out for some work, not able do anything for project today.

## Week 8

- Jul 19:
  - Worked on CAN bus, submitted a [PR](https://github.com/beagleboard/bb.org-overlays/pull/189) for CAN0 & CAN1
- Jul 20:
  - Started working on UART, I2C, SPI, PWM.
- Jul 21:
  - Submitted [PR](https://github.com/beagleboard/bb.org-overlays/pull/193) for bone bus PWM DT overlays.
- Jul 22 - 25:
  - Worked on documentation and examples
    - Updated [Cape Interface Spec](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec) page.
- Jul 26:
  - Started working on the cape examples.

## Week 9

- Jul 27:
  - Started working on pwm-timer.
- Jul 28:
  - submitted [PR](https://github.com/beagleboard/bb.org-overlays/pull/195) for pwm-timer.
- Jul 29:
  - Did some reading on PRU.
- Jul 30 & 31:
  - Break from work due to EXAM (BTP presentation).
- Aug 1:
  - Started working on PRU & ADC.
- Aug 2:
  - got cloud9 PRU examples to work on BBAI.

## Week 10

- Aug 3:
  - got PRU1_0 & PRU1_1 to work on BBAI, wrote overlays and cloud9 examples for it.
- Aug 4:
  - tried rcn-ee's testing image (v5.4x)
- Aug 5:
  - tested PRU macros.
- Aug 6:
  - Updated cape interface spec.
- Aug 7:
  - Worked on PRU examples.
- Aug 8:
  - Started working on v5.4x kernel for BBAI
- Aug 9:
  - Got BBBWL working with ecn-ee's testing image.
  
## Week 11

- Aug 10:
  - Not able to make the compatibility code to work on v5.4x-ti-overlay branch.
- Aug 11:
  - Tried merging compatibility code uisng meld but things didn't work out well.
  - rcn-ee's creating 4.19x-ti-overlays and that will solve the issue hopefully.
- Aug 12:
  - Compatibility layer got merged into v4.19.x-ti-overlays branch.
- Aug 13:
  - Submitted [UART console](https://github.com/beagleboard/cloud9-examples/pull/46) example to cloud9-examples.
- Aug 14:
  - updted blinkR30 examples [PR](https://github.com/beagleboard/cloud9-examples/pull/45#issuecomment-674055684).
- Aug 15:
  - Independence Day break 🤩
- Aug 16:
  - added McASP nodes and labels for BBBWL, BBB and BBAI.

## Week 12

- Aug 17:
  - added eCAP pinmux nodes.
  - started working on eQEP.
- Aug 18:
  - Completed McASP, eCAP, ADC, and eQEP DT nodes.
- Aug 19:
  - [compatibility_update1](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/20) has been merged.
- Aug 20:
  - Started working on compatibility_update2.
- Aug 21:
  - Worked in compatibility_update2.
- Aug 22:
  - Created new nodes and cleaned up things for compatibility_update2.
- Aug 23:
  - Completed compatibility_update2 coding.
  - Started Testing i.e. Loading each overlays on boards.

## Week 13

- Aug 24:
  - Compatibility update got [merged](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/21).
- Aug 25:
  - looking into TI SDK for LCD solution.
- Aug 26:
  - Started Working on this site, updated page handling.
  - New Table of content file `/_data/toc.yaml` for finer control.
- Aug 27:
  - Created new collapsable item for `site.description`, press 📌to see the message.
  - Updated Blog page for better pagination.
  - LCD4 is working with BBAI now! 
    - [BBAI-4D4C-00A1.dts](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/compatibility_Update3/src/arm/overlays/BBAI-4D4C-00A1.dts)
- Aug 28:
  - Finalized [cape interface spec](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec) page.
- Aug 29:
  - Updated this site, ready to submit GSoC final report.
- Aug 30:
