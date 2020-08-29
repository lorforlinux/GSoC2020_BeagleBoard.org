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

# Achieved Milestones

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








