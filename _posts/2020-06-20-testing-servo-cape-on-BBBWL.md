---
layout: post
title:  Testing servo cape on BBBWL/BBB
---

BBORG servo cape uses PCA9685 PWM chip for it's 16 servo outputs. You can control the servos by writing to 0x70 of /dev/i2c-2 But, here we well see how you can enable the pwm-pca9685 kernel driver using an overlay. We will also see how you can use a simple script that uses sysfs to control the servos.

<p class="message" style="color:red;"> Note: Links to overlay and test script files may change as this post is written as part of the development process!</p>

## The overlay

To install the overlay on your BBB execute these commands, <i style="color:green">$</i> and <i style="color:red">#</i> before any command depicts <i style="color:green">normal user command</i> and <i style="color:red">super user command</i> respectively :)

``` instructions
Become super-user
$ su
OR
$ sudo su

Change to bb.org-overlays directory
# cd /opt/source/bb.org-overlays/src/arm

Download the DT overlay
# wget https://raw.githubusercontent.com/lorforlinux/bb.org-overlays/servo/src/arm/BBORG_SERVO-00A2.dts

Compile the overlay
# cd ../../
# make src/arm/BBORG_SERVO-00A2.dtbo

Install the overlay
# cp src/arm/BBORG_SERVO-00A2.dtbo /lib/firmware
```

Make sure you have not edited /boot/uEnv.txt to include any overlay at addr0!

## Checking if it worked :)

shutdown your board using this command

``` instructions
# shutdown -h now
```

Insert your cape onto your BBB and start your board. First we check if the overlay is loaded perfectly.

``` instructions
Check if overlay loaded
$ cd /proc/device-tree/chosen/overlays/
$ ls

You should see the servo cape loaded here!
```

Now we check the driver is loaded fine, for doing that execute these commands,

``` instructions
This should not give any errors
$ cd /sys/class/i2c-adapter/i2c-2/2-0070/pwm

You sould see a pwmchip here
$ ls
```

## Testing servo control

Before testing any servo make sure you have provided 5V input through terminal power block (Blue thing with screws)!

Now execute these commands to test the servo on S1 servo output of the cape :)

``` instructions
Go to HOME
$ cd ~

Download the script
$ wget https://raw.githubusercontent.com/lorforlinux/BeagleBone-Examples/master/ServoCape_test.sh

Make it executable
$ chmod +x ServoCape_test.sh

Run it
$ ./ServoCape_test.sh
```

You should see the servo moving!
