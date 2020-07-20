---
layout: post
title:  Using bone bus I2C on BBBWL/BBB/BBAI
---

In this post we will take a look at how you can use the new [compatibility layer](https://github.com/beagleboard/BeagleBoard-DeviceTrees/pull/17) along with some new bone bus DT overlays to setup `/dev/bone/i2c/*` on your BBBWL/BBB/BBAI.

<p class="message" style="color:red;"> Note: You must correctly install the compatibility layer on your system before following the steps else you'll end up with your board not booting. It is recommended to boot the board from an sdCard so that you can edit back the /boot/uEnv.txt if your board didn't boot!</p>

## 🐾 Installing the compatibility layer

Please refer to the ["Installing compatibility layer on your BBBWL/BBB/BBAI"](https://lorforlinux.github.io/GSoC2020_BeagleBoard.org/2020/07/19/installing-compatibility-layer/) post for this.

## 🐾 bone bus i2c

We have these i2c peripherals available to use:

|bone bus        |BBBWL/BBB |BBAI |I2C SCL |I2C SDA  |
|:---:           |:---:     |:---:|:---:   |:---:    |
|/dev/bone/i2c/1 |I2C1      |I2C5 |P9.17   |P9.18    |
|/dev/bone/i2c/2 |I2C2      |I2C4 |P9.19   |P9.20    |
|/dev/bone/i2c/2a|I2C2      |N/A  |P9.21   |P9.22    |
|/dev/bone/i2c/3 |I2C1      |I2C3 |P9.24   |P9.26    |

Note: If you are using BBBWL/BBB you can not use both `/dev/bone/i2c/1` and `/dev/bone/i2c/3` at the same time as they both use I2C1, same goes for `/dev/bone/i2c/2` and `/dev/bone/i2c/2a` as they both use I2C2!

## 🐾 Installing /dev/bone/i2c/* DT overlays

- Clone the repository, `$ git clone https://github.com/lorforlinux/bb.org-overlays.git`.
- Change directory, `$ cd bb.org-overlays`.
- Change branch, `$ git checkout bone_i2c`.
- Compile overlays, `$ make`.
- To cleanup the binaries you can use, `$ make clean`.
- Install bone i2c DT overlays, `$ sudo cp src/arm/BONE-I2C{1,2,2A,3}-00A0.dtbo /lib/firmware/`.

Now, you are all set to use the overlays!

## 🐾 Loading the oeralys using /boot/uEnv.txt

To load the overlays during boot you have to edit `/boot/uEnv.txt`. You can use either `nano` OR `vim` to edit the file. There are total 8 slots for overlays which we can use, `uboot_overlay_{addr0 - addr3}` are used to override cape with EEPROM and `uboot_overlay_{addr4 - addr7}` are used for additional custom capes. I suggest to use `uboot_overlay_{addr4 - addr7}` for bone i2c virtual capes but, You can use any to load the overlay.

To load the capes you can uncomment the lines for the slots if they are already present in the `/boot/uEnv.txt` but commented out as we see on BBBWl/BBB's `uEnv.txt`. If by any chance they are not present you can copy paste them form below. You can learn more about u-boot SPL overlays [here](https://forum.digikey.com/t/all-beaglebone-varients-u-boot-overlays/26/2)!

```

enable_uboot_overlays=1

#uboot_overlay_addr4=/lib/firmware/BONE-I2C1-00A0.dtbo
#uboot_overlay_addr5=/lib/firmware/BONE-I2C2-00A0.dtbo
#uboot_overlay_addr6=/lib/firmware/BONE-I2C2A-00A0.dtbo
#uboot_overlay_addr7=/lib/firmware/BONE-I2C3-00A0.dtbo

```

Now, you can uncomment the overlay(s) you want to load during boot. Just keep in mind that you can not use both `/dev/bone/i2c/1` and `/dev/bone/i2c/3` at the same time as they both use I2C1, same goes for `/dev/bone/i2c/2` and `/dev/bone/i2c/2a` as they both use I2C2. For BBAI we don't have `/bone/i2c/2a` available so loading overlay `/lib/firmware/BONE-I2C2A-00A0.dtbo` will not do anything on BBAI. 

<p class="message" style="color:purple;"> Tip: If you have any suggestion/feedback OR facing any problem create an issue in <a href="https://github.com/lorforlinux/bb.org-overlays/tree/bone_i2c">this</a> repository, Thank you :) </p>