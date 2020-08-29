---
layout: default
title: Home
---

<div class="text-center">
    <a href="https://elinux.org/BeagleBoard/GSoC/2020_Projects/Cape_Compatibility" target="_blank">
        <img src="public/projectBanner.png" class="border border-danger rounded img-fluid" alt="banner">
    </a>
</div>

<p class="text-center message border border-warning bg-dark text-warning">
    The idea of this project was to make the same user space examples work with both 
    BeagleBone Black and BeagleBone AI, using the same references to drivers for 
    peripherals assigned to the same pins between BeagleBone Black and BeagleBone AI.
    Also, Same DT overlays should work (whenever possible) for both BBB and BBAI, with 
    updated uBoot cape manager DT overlays will be automatically loaded during boot.
</p>

<a href="https://beagleboard.org/latest-images" 
    class="btn btn-warning btn-block text-dark" 
    role="button" aria-pressed="true" target="_blank">
    Download BeagleBoard.org Latest Firmware Images to use Compatibility layer! 
</a>
 
---

# {% octicon mortar-board height:24 %} Achieved Milestones

- Created (if achievable) and tested compatibility layer for Bone Buses on BBBWL, BBB, and BBAI. Checkout links below for more detials on each Bone Bus.
    1. [LEDs](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#LEDs)
    2. [I2C](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#I2C)
    3. [SPI](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#SPI)
    4. [UART](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#UART)
    5. [CAN](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#CAN)
    6. [ADC](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#ADC)
    7. [PWM](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#PWM)
    8. [TIMER PWM](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#TIMER_PWM)
    9. [eCAP](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#eCAP)
    10. [eMMC](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#eMMC)
    11. [LCD](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#LCD)
    12. [eQEP](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#eQEP)
    13. [McASP](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#McASP)
    14. [PRU](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#PRU)
- Created compatible overlays for these capes using the bone bus compatibility layer,
    - [Load Cape](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_LOAD-00A2.dts).
    - [Motor Cape](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_MOTOR-00A2.dts).
    - [Relay Cape](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_RELAY-00A2.dts).
    - [Sero Cape](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_SERVO-00A2.dts).
    - [Comms Cape](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_COMMS-00A2.dts).
- Got 4.3" Display Cape to work on BBAI.
- Refactored code in [Beagle Tester](https://github.com/jadonk/beagle-tester) repository.
- Created new userspace examples in [cloud9-examples](https://github.com/beagleboard/cloud9-examples) repo.
- Finalized [cape interface spec](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec) page.


Project milestones list can be found on `elinux.org` [here](https://elinux.org/BeagleBoard/GSoC/2020_Projects#Milestones).

---

# {% octicon git-pull-request height:24 %} Pull Requests

<div class="message">
Only those PRs that are submitted during GSoC period are shown here. You can check my other PRs on the repo page for more info on Compatibility layer and related code.
</div>

<!-- BeagleBoard-DeviceTrees -->
<div class="text-center text-dark border border-warning bg-warning">
    <a href="https://github.com/beagleboard/BeagleBoard-DeviceTrees">
        {% octicon repo height:16 %} beagleboard/BeagleBoard-DeviceTrees
    </a>
</div>

| PR     | Status |
| :---------: | :--: |
|[Compatibility layer update2](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/21)| Merged |
|[Compatibility layer update1](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/20)| Merged |
|[Update Makefile to support overlays](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/19)| Closed |
|[Cape compatibility layer for BeagleBone Black and BeagleBone AI](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/18)| Merged |
|[Compatibility](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17)| Closed|
|[add comments to am5729-beagleboneai.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/15)| Merged |

<!--  -->
<div class="text-center text-dark border border-danger bg-warning">
    <a href="https://github.com/beagleboard/cloud9-examples">
        {% octicon repo height:16 %}  beagleboard cloud9-examples
    </a>
</div>

| PR     | Status |
| :---------: | :--: |
|[blinkR30 examples for PRU BBAI](https://github.com/beagleboard/cloud9-examples/pull/45)| Open |
|[LoadCape: Example for toggling each load](https://github.com/beagleboard/cloud9-examples/pull/43)| Open |
|[UART console](https://github.com/beagleboard/cloud9-examples/pull/46)| Merged |
|[Correct sensors link and add displays link](https://github.com/beagleboard/cloud9-examples/pull/37)| Merged |

<!-- BeagleBoard-DeviceTrees -->
<div class="text-center text-dark border border-warning bg-warning">
    <a href="https://github.com/beagleboard/bb.org-overlays">
        {% octicon repo height:16 %} beagleboard/bb.org-overlays
    </a>
</div>
This repository hosted initial Compatible DT overlays but, along with a new uBoot update the location of the compatible overlays has been updated to {% octicon repo height:16 %} [beagleboard/BeagleBoard-DeviceTrees](https://github.com/beagleboard/BeagleBoard-DeviceTrees). Although the submitted code no longer required to be merged, Some of the PRs I submitted are listed below and you can visit the {% octicon repo height:16 %} [bb.org-overlays](https://github.com/beagleboard/bb.org-overlays) repo to see more.


| PR     | Status |
| :---------: | :--: |
|[Bone spi](https://github.com/beagleboard/bb.org-overlays/pull/183)| Open |
|[Bone i2c](https://github.com/beagleboard/bb.org-overlays/pull/182)| Open |
|[Bone uart](https://github.com/beagleboard/bb.org-overlays/pull/180)| Open |
|[Bone can](https://github.com/beagleboard/bb.org-overlays/pull/189)| Open |

<!-- BeagleBoard-DeviceTrees -->
<div class="text-center text-dark border border-warning bg-warning">
    <a href="https://github.com/jadonk/beagle-tester">
        {% octicon repo height:16 %}  jadonk/beagle-tester 
    </a>
</div>

| PR     | Status |
| :---------: | :--: |
|[Initial Code Refactoring of beagle-tester.c](https://github.com/jadonk/beagle-tester/pull/23)| Merged |

<!-- {% octicon issue-closed height:24 %}
{% octicon issue-opened height:24 %}
{% octicon git-merge height:24 %} -->

---





