---
layout: post
title:  Installing compatibility layer on your BBBWL/BBB/BBAI
---

The compatibility layer is a new abstraction layer that allows us to create one overlays that work on BBBWL, BBB, and BBAI without any change. In this post, we will take a look at how you can install this on your board. It's a work in progress at this moment and not all the functionality is implemented yet. The new code will not interfere with anything previously written for the board.

While testing I suggest you flash [the latest image](https://beagleboard.org/latest-images) on an SD card and use it instead of flashing the image on the onboard eMMC. Using SD Card will allow you to set things up back to normal through your computer if the board doesn't boot after making the changes.

<p class="message" style="color:red;"> Note: We will be using kernel v4.19x for testing compatibility layer. If you are using v4.14x with minor changes in commands things will work out fine but I don't recommend using anything below v4.14x!</p>

## 🐾 Preparing SD Card

Go to [the latest images](https://beagleboard.org/latest-images) page and download the image for your board OR click on the link(s) below to download the version I used while testing.

- BBAI:  [AM5729 Debian 10.3 2020-04-06 6GB SD IoT TIDL](https://debian.beagleboard.org/images/am57xx-debian-10.3-iot-tidl-armhf-2020-04-06-6gb.img.xz)
- BBBWl/BBB: [AM3358 Debian 10.3 2020-04-06 4GB SD IoT](https://debian.beagleboard.org/images/bone-debian-10.3-iot-armhf-2020-04-06-4gb.img.xz)

You'll also require flasher like [balenaEtcher](https://www.balena.io/etcher/) to flash the image onto your SD Card.

## 🐾 Create dtb backup

After flashing the SD Card, insert it onto your board and it will boot from SD Card automatically. After the connection has been established ssh onto your board using `$ ssh debian@192.168.7.2` and give password `temppwd`. You might have to run `$ sudo apt update -y && sudo apt upgrade -y` on your board. This step will allow us to revert to the original state if things don't work out right for you. We are using v4.19x here, If you are using v4.14x you must change the command accordingly.

- BBAI: `$ sudo cp /boot/dtbs/4.19*/am5729-beagleboneai.dtb am5729-beagleboneai.dtb.backup`.
- BBBWL/BBB: `$ sudo cp /boot/dtbs/4.19*/am335x-boneblack-uboot-univ.dtb am335x-boneblack-uboot-univ.dtb.backup`.

If dtc is not installed you can install it using, `$ sudo apt install device-tree-compiler`.

## 🐾 Installing the compatibility layer

- Clone the repository, `$ git clone https://github.com/lorforlinux/BeagleBoard-DeviceTrees.git`.
- Change directory, `$ cd BeagleBoard-DeviceTrees`.
- Make sure you are on `v4.19.x-ti` branch using `$ git branch`. If you are not change branch using `$ git checkout v4.19.x-ti`.
- Compile code, `$ make`.
- To cleanup the binaries you can use, `$ make clean`.
- Install the dtb file on your board, make sure you have created the backup before doing this.
  - BBBWL/BBB: `$ sudo cp src/arm/am335x-boneblack-uboot-univ.dtb /boot/dtbs/4.19*/`.
  - BBAI: `$ sudo cp src/arm/am5729-beagleboneai.dtb /boot/dtbs/4.19*/`.
- Reboot your board, `$ sudo reboot`.

Your compatibility layer code is now set up correctly and you can try using new bone bus DT overlays on your board (BBBWL/BBB/BBAI).

## 🐾 Reverting to old dtb

If you wish to revert things to the original you can do that. Use a card reader and mount rootfs on your PC. now go to `/boot/dtbs/4.19*/` and open up a terminal there.

- Remove the newly installed dtb,
  - BBBWL/BBB: `$ sudo rm am335x-boneblack-uboot-univ.dtb`.
  - BBAI: `$ sudo rm am5729-beagleboneai.dtb`.
- Use old dtb,
  - BBBWL/BBB: `$ sudo cp am335x-boneblack-uboot-univ.dtb.backup am335x-boneblack-uboot-univ.dtb`.
  - BBAI: `$ sudo cp am5729-beagleboneai.dtb.backup am5729-beagleboneai.dtb`.
- Optional: remove backup dtb,
  - BBBWL/BBB: `$ sudo rm am335x-boneblack-uboot-univ.dtb.backup`.
  - BBAI: `$ sudo rm am5729-beagleboneai.dtb.backup`.

<p class="message" style="color:purple;"> Tip: If you have any suggestion/feedback OR facing any problem create an issue in <a href="https://github.com/lorforlinux/BeagleBoard-DeviceTrees/tree/v4.19.x-ti">this</a> repository, Thank you :) </p>
