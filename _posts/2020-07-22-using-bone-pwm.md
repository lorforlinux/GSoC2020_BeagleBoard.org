---
layout: post
title:  Using bone bus PWM on BBBWL/BBB/BBAI
---

In this post we will take a look at how you can use the new [compatibility layer](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17) along with some new bone bus DT overlays to setup `/dev/pwm/*` on your BBBWL/BBB/BBAI.

<p class="message" style="color:red;"> Note: You must correctly install the compatibility layer on your system before following the steps else you'll end up with your board not booting. It is recommended to boot the board from an sdCard so that you can edit back the /boot/uEnv.txt if your board didn't boot!</p>

## 🐾 Installing the compatibility layer

Please refer to the ["Installing compatibility layer on your BBBWL/BBB/BBAI"](https://lorforlinux.github.io/GSoC2020_BeagleBoard.org/2020/07/19/installing-compatibility-layer/) post for this.

## 🐾 bone bus i2c

We have these pwm peripherals available, which can be accessed from `/dev/pwm/*` when enabled,

|bone bus |BBBWL/BBB       |BBAI              |PWM A |PWM B |
|:---:    |:---:           |:---:             |:---: |:---: |
|pwm0     |PWM0 (ehrpwm0*) |N/A               |P9.22 |P9.21 |
|pwm1     |PWM1 (ehrpwm1*) |PWM3 (ehrpwm2*)   |P9.14 |P9.16 |
|pwm2     |PWM2 (ehrpwm2*) |PWM2 (ehrpwm1*)   |P9.19 |P9.13 |

Where PWM A will be `/dev/pwm/ehrpwm*a/` and PWM B will be `/dev/pwm/ehrpwm*b/`.
## 🐾 Installing DT overlays

- Clone the repository, `$ git clone https://github.com/lorforlinux/bb.org-overlays.git`.
- Change directory, `$ cd bb.org-overlays`.
- Change branch, `$ git checkout bone_pwm`.
- Compile overlays, `$ make`.
- Install bone i2c DT overlays, `$ sudo cp src/arm/BONE-PWM{0,1,2}.dtbo /lib/firmware/`.
- To cleanup the binaries you can use, `$ make clean`.

Now, you are all set to use the overlays!

## 🐾 Loading the overalys using /boot/uEnv.txt

To load the overlays during boot you have to edit `/boot/uEnv.txt`. You can use either `nano` OR `vim` to edit the file. There are total 8 slots for overlays which we can use, `uboot_overlay_{addr0 - addr3}` are used to override cape with EEPROM and `uboot_overlay_{addr4 - addr7}` are used for additional custom capes. I suggest to use `uboot_overlay_{addr4 - addr7}` for PWM virtual capes but, You can use any to load the overlay.

To load the capes you can uncomment the lines for the slots and add the overlay (/lib/firmware/BONE-PWM*.dtbo), if they are already present in the `/boot/uEnv.txt`! but commented out as we see on BBBWl/BBB's `uEnv.txt`. If by any chance they are not present you can copy paste them form below. You can learn more about u-boot SPL overlays [here](https://forum.digikey.com/t/all-beaglebone-varients-u-boot-overlays/26/2)!

```

enable_uboot_overlays=1

#uboot_overlay_addr4=/lib/firmware/BONE-PWM0.dtbo
#uboot_overlay_addr5=/lib/firmware/BONE-PWM1.dtbo
#uboot_overlay_addr6=/lib/firmware/BONE-PWM2.dtbo

```

Now, you can uncomment the overlay(s) you want to load during boot.

## 🐾 Testing PWM

Before testing it make sure your PWM overlay loaded successfully using `$ ls /proc/device-tree/chosen/overlays/`. Now, you have to change directory to `/dev/pwm/ehrpwm*` (see the above table for this). To test the PWM output using LED you need to set period and duty_cycle then enable the output, like this:

```
For example
$ cd /dev/pwm/ehrpwm0a/

Setup PWM output
$ echo 50000 > period 
$ echo 50000 > duty_cycle 
$ echo 1 > enable
```

Now you can change the intensity by changing the duty_cycle, `500 = 0%` & `50000 = 100%`.

<p class="message" style="color:purple;"> Tip: If you have any suggestion/feedback OR facing any problem create an issue in <a href="https://github.com/lorforlinux/bb.org-overlays/tree/bone_pwm">this</a> repository, Thank you :) </p>