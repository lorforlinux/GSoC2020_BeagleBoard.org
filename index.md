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


<div class="card">
  <div class="card-header bg-dark text-light text-center">
    Installing Compatibility Layer
  </div>
  <div class="card-body">
    <!-- Section A -->
    <h2 class="card-title">1. Update and Upgrade your system</h2>
    <!-- Step 1 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo apt update -y" id="A1" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('A1')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
    <!-- Step 2 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo apt upgrade -y" id="A2" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('A2')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
    <!-- Step 3 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo reboot" id="A3" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('A3')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
    <!-- Section B -->
    <h2 class="card-title">2. Update Kernel</h2>
    <!-- Step 1 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo /opt/scripts/tools/update_kernel.sh --lts-4_19" id="B1" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('B1')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
    <!-- Step 2 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo reboot" id="B2" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('B2')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
    <!-- Section C -->
    <h2 class="card-title">3. Update Bootloader</h2>
    <!-- Step 1 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo /opt/scripts/tools/developers/update_bootloader.sh" id="C1" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('C1')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
    <!-- Step 2 -->
    <div class="input-group mb-3">
        <div class="input-group-prepend">
            <span class="input-group-text" id="inputGroup-sizing-sm">&#36;</span>
        </div>
        <input type="text" class="bg-light form-control" value="sudo reboot" id="C2" disabled>
        <div class="input-group-append">
            <button class="btn btn-outline-secondary copy" type="button" onclick="copy2Clipboard('C2')"><span class="fa fa-copy"></span></button>
        </div>
    </div>
  </div>
</div>

---

# {% octicon shield-check height:24 %} Achieved Milestones

<div class="message">
    Only major milestones has been shown here! you can see the entire Project milestones list 
    on the BeagleBoard GSoC 2020 Projects elinux.org page <a href="https://elinux.org/BeagleBoard/GSoC/2020_Projects#Milestones">here</a>.
</div>

<div class="text-center text-dark border border-warning bg-dark">
    <a href="https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec" style="color:#ffc107; fill:#ffc107">
        Created (when achievable) and tested compatibility layer for Bone Buses on BBBWL, BBB, and BBAI. Checkout links below for more detials like Header pin reference for each Bone Bus and Complimentary DT overlay which I created during GSoC time period.
    </a>
</div>

| 1. [LEDs](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#LEDs) | 8. [TIMER PWM](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#TIMER_PWM) |
| 2. [I2C](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#I2C) | 9. [eCAP](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#eCAP) |
| 3. [SPI](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#SPI) | 10. [eMMC](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#eMMC) |
| 4. [UART](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#UART) | 11. [LCD](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#LCD) |
| 5. [CAN](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#CAN) | 12. [eQEP](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#eQEP) |
| 6. [ADC](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#ADC) | 13. [McASP](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#McASP) |
| 7. [PWM](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#PWM) | 14. [PRU](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec#PRU) |

<div class="text-center text-dark border border-warning bg-dark">
    <a href="https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/compatibility_Update3/src/arm/overlays/" style="color:#ffc107; fill:#ffc107">
        Created compatible overlays for these capes using the bone bus compatibility layer
    </a>
</div>

| Cape | Compatible Overlay |
| :-----: | :-----: |
| Load | [BBORG_LOAD-00A2.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_LOAD-00A2.dts) |
| Motor | [BBORG_MOTOR-00A2.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_MOTOR-00A2.dts) |
| Relay | [BBORG_RELAY-00A2.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_RELAY-00A2.dts) |
| Sero | [BBORG_SERVO-00A2.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_SERVO-00A2.dts) |
| Comms | [BBORG_COMMS-00A2.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBORG_COMMS-00A2.dts) |

<div class="text-center text-dark border border-warning bg-dark">
    <a href="https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/compatibility_Update3/src/arm/overlays/" style="color:#ffc107; fill:#ffc107">
        Got 4.3" Display Cape to work on BBAI.
    </a>
</div>

| Cape | Overlay |
| :-----: | :-----: |
| 4D Systems GEN4-4DCAPE-43CT-CLB | [BBAI-4D4C-00A1.dts](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/compatibility_Update3/src/arm/overlays/BBAI-4D4C-00A1.dts) |

<!-- - Refactored code in [Beagle Tester](https://github.com/jadonk/beagle-tester) repository.
- Created new userspace examples in [cloud9-examples](https://github.com/beagleboard/cloud9-examples) repo.
- Finalized [cape interface spec](https://elinux.org/Beagleboard:BeagleBone_cape_interface_spec) page. -->

---

# {% octicon git-pull-request height:24 %} Pull Requests

<div class="message">
Only those PRs that are submitted during GSoC period are shown here. You can check my other PRs on the repo page for more info on Compatibility layer and related code.
</div>

<!-- BeagleBoard-DeviceTrees -->
<div class="text-center text-dark border border-warning bg-dark">
    <a href="https://github.com/beagleboard/BeagleBoard-DeviceTrees" style="color:#ffc107; fill:#ffc107">
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

<!-- cloud9-examples -->
<div class="text-center text-dark border bg-dark">
    <a href="https://github.com/beagleboard/cloud9-examples" style="color:#ffc107; fill:#ffc107">
        {% octicon repo height:16 %}  beagleboard cloud9-examples
    </a>
</div>

| PR     | Status |
| :---------: | :--: |
|[blinkR30 examples for PRU BBAI](https://github.com/beagleboard/cloud9-examples/pull/45)| Open |
|[LoadCape: Example for toggling each load](https://github.com/beagleboard/cloud9-examples/pull/43)| Open |
|[UART console](https://github.com/beagleboard/cloud9-examples/pull/46)| Merged |
|[Correct sensors link and add displays link](https://github.com/beagleboard/cloud9-examples/pull/37)| Merged |

<!-- bb.org-overlays -->
<div class="text-center text-dark border border-warning bg-dark">
    <a href="https://github.com/beagleboard/bb.org-overlays" style="color:#ffc107; fill:#ffc107">
        {% octicon repo height:16 %} beagleboard/bb.org-overlays
    </a>
</div>


This repository hosted initial Compatible DT overlays but, along with new uBoot update the location of the compatible overlays has been updated to {% octicon repo height:16 %} [beagleboard/BeagleBoard-DeviceTrees](https://github.com/beagleboard/BeagleBoard-DeviceTrees). Some of the PRs I submitted are listed below, You can visit the {% octicon repo height:16 %} [bb.org-overlays](https://github.com/beagleboard/bb.org-overlays) repo to see more. The submitted code is no longer required to be merged!


| PR     | Status |
| :---------: | :--: |
|[Bone spi](https://github.com/beagleboard/bb.org-overlays/pull/183)| Open |
|[Bone i2c](https://github.com/beagleboard/bb.org-overlays/pull/182)| Open |
|[Bone uart](https://github.com/beagleboard/bb.org-overlays/pull/180)| Open |
|[Bone can](https://github.com/beagleboard/bb.org-overlays/pull/189)| Open |

<!-- BeagleBoard-DeviceTrees -->
<div class="text-center text-dark border border-warning bg-dark">
    <a href="https://github.com/jadonk/beagle-tester" style="color:#ffc107; fill:#ffc107">
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





