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
    Also, Same DT overlays should work (whenever possible) for both BBB and BBAI, with updated uBoot cape manager
    DT overlays will be automatically loaded during boot.
</p>

<a href="https://beagleboard.org/latest-images" 
    class="btn btn-warning btn-block text-dark" 
    role="button" aria-pressed="true" target="_blank">
    Download latest image to use Compatibility layer! 
</a>
 
---

# Achieved Goals

- Created (when possible) and tested compatibility layer  for Bone Buses on BBBWL, BBB, and BBAI. Checkout links below for more detials.
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
- Using compatibility layer created compatible overlays for these capes,
    - Load Cape.
    - Motor Cape.
    - Relay Cape.
    - Sero Cape.
    - Comms Cape.
- Got 4.3" Display Cape to work on BBAI (no compatibility layer for LCD).
- Cleaned up Beagle Tester.


A more detailed milestones list can be found [here](https://elinux.org/BeagleBoard/GSoC/2020_Projects#Milestones).

---








