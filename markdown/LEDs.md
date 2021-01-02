---
layout: default
permalink: /LEDs/
---

# Bone LEDs
The compatibility layer comes with simple reference nodes for attaching LEDs to any gpio pin. The format followed for these nodes is `led_P8_##`/`led_P9_##`. The `gpio-leds` driver is used by these reference nodes internally and allows users to easily create compatible led nodes in overlays for BBBWL, BBB, and BBAI. For the definitions, you can see [bbai-bone-buses.dtsi#L16](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbai-bone-buses.dtsi#L16) & [bbb-bone-buses.dtsi#L16](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbb-bone-buses.dtsi#L16).

### Example Overlays

- Led attached to P9.11, [BONE-LED_P9_11.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BONE-LED_P9_11.dts)
- Led attached to P8.03, [BONE-LED_P8_03.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BONE-LED_P8_03.dts)


<div class="text-center text-dark border border-warning bg-dark">
    <a style="color:#ffc107; fill:#ffc107">
        Bone LED reference chart
    </a>
</div>

| LED  |	Header pin |	BBBWL/BBB |	BBAI |
| :--: | :--:          |    :--:      | :--: |
| /sys/class/leds/led_P8_03 | 	P8_03 | 	gpio1_6 | 	gpio1_24 |
| /sys/class/leds/led_P8_04 | 	P8_04 | 	gpio1_7 | 	gpio1_25 |
| /sys/class/leds/led_P8_05 | 	P8_05 | 	gpio1_2 | 	gpio7_1 |
| /sys/class/leds/led_P8_06 | 	P8_06 | 	gpio1_3 | 	gpio7_2 |
| /sys/class/leds/led_P8_07 | 	P8_07 | 	gpio2_2 | 	gpio6_5 |
| /sys/class/leds/led_P8_08 | 	P8_08 | 	gpio2_3 | 	gpio6_6 |
| /sys/class/leds/led_P8_09 | 	P8_09 | 	gpio2_5 | 	gpio6_18 |
| /sys/class/leds/led_P8_10 | 	P8_10 | 	gpio2_4 | 	gpio6_4 |
| /sys/class/leds/led_P8_11 | 	P8_11 | 	gpio1_13 | 	gpio3_11 |
| /sys/class/leds/led_P8_12 | 	P8_12 | 	gpio1_12 | 	gpio3_10 |
| /sys/class/leds/led_P8_13 | 	P8_13 | 	gpio0_23 | 	gpio4_11 |
| /sys/class/leds/led_P8_14 | 	P8_14 | 	gpio0_26 | 	gpio4_13 |
| /sys/class/leds/led_P8_15 | 	P8_15 | 	gpio1_15 | 	gpio4_3 |
| /sys/class/leds/led_P8_16 | 	P8_16 | 	gpio1_14 | 	gpio4_29 |
| /sys/class/leds/led_P8_17 | 	P8_17 | 	gpio0_27 | 	gpio8_18 |
| /sys/class/leds/led_P8_18 | 	P8_18 | 	gpio2_1 | 	gpio4_9 |
| /sys/class/leds/led_P8_19 | 	P8_19 | 	gpio0_22 | 	gpio4_10 |
| /sys/class/leds/led_P8_20 | 	P8_20 | 	gpio1_31 | 	gpio6_30 |
| /sys/class/leds/led_P8_21 | 	P8_21 | 	gpio1_30 | 	gpio6_29 |
| /sys/class/leds/led_P8_22 | 	P8_22 | 	gpio1_5 | 	gpio1_23 |
| /sys/class/leds/led_P8_23 | 	P8_23 | 	gpio1_4 | 	gpio1_22 |
| /sys/class/leds/led_P8_24 | 	P8_24 | 	gpio1_1 | 	gpio7_0 |
| /sys/class/leds/led_P8_25 | 	P8_25 | 	gpio1_0 | 	gpio6_31 |
| /sys/class/leds/led_P8_26 | 	P8_26 | 	gpio1_29 | 	gpio4_28 |
| /sys/class/leds/led_P8_27 | 	P8_27 | 	gpio2_22 | 	gpio4_23 |
| /sys/class/leds/led_P8_28 | 	P8_28 | 	gpio2_24 | 	gpio4_19 |
| /sys/class/leds/led_P8_29 | 	P8_29 | 	gpio2_23 | 	gpio4_22 |
| /sys/class/leds/led_P8_30 | 	P8_30 | 	gpio2_25 | 	gpio4_20 |
| /sys/class/leds/led_P8_31 | 	P8_31 | 	gpio0_10 | 	gpio8_14 |
| /sys/class/leds/led_P8_32 | 	P8_32 | 	gpio0_11 | 	gpio8_15 |
| /sys/class/leds/led_P8_33 | 	P8_33 | 	gpio0_9 | 	gpio8_13 |
| /sys/class/leds/led_P8_34 | 	P8_34 | 	gpio2_17 | 	gpio8_11 |
| /sys/class/leds/led_P8_35 | 	P8_35 | 	gpio0_8 | 	gpio8_12 |
| /sys/class/leds/led_P8_36 | 	P8_36 | 	gpio2_16 | 	gpio8_10 |
| /sys/class/leds/led_P8_37 | 	P8_37 | 	gpio2_14 | 	gpio8_8 |
| /sys/class/leds/led_P8_38 | 	P8_38 | 	gpio2_15 | 	gpio8_9 |
| /sys/class/leds/led_P8_39 | 	P8_39 | 	gpio2_12 | 	gpio8_6 |
| /sys/class/leds/led_P8_40 | 	P8_40 | 	gpio2_13 | 	gpio8_7 |
| /sys/class/leds/led_P8_41 | 	P8_41 | 	gpio2_10 | 	gpio8_4 |
| /sys/class/leds/led_P8_42 | 	P8_42 | 	gpio2_11 | 	gpio8_5 |
| /sys/class/leds/led_P8_43 | 	P8_43 | 	gpio2_8 | 	gpio8_2 |
| /sys/class/leds/led_P8_44 | 	P8_44 | 	gpio2_9 | 	gpio8_3 |
| /sys/class/leds/led_P8_45 | 	P8_45 | 	gpio2_6 | 	gpio8_0 |
| /sys/class/leds/led_P8_46 | 	P8_46 | 	gpio2_7 | 	gpio8_1 |
| /sys/class/leds/led_P9_11 | 	P9_11 | 	gpio0_30 | 	gpio8_17 |
| /sys/class/leds/led_P9_12 | 	P9_12 | 	gpio1_28 | 	gpio5_0 |
| /sys/class/leds/led_P9_13 | 	P9_13 | 	gpio0_31 | 	gpio6_12 |
| /sys/class/leds/led_P9_14 | 	P9_14 | 	gpio1_18 | 	gpio4_25 |
| /sys/class/leds/led_P9_15 | 	P9_15 | 	gpio1_16 | 	gpio3_12 |
| /sys/class/leds/led_P9_16 | 	P9_16 | 	gpio1_19 | 	gpio4_26 |
| /sys/class/leds/led_P9_17 | 	P9_17 | 	gpio0_5 | 	gpio7_17 |
| /sys/class/leds/led_P9_18 | 	P9_18 | 	gpio0_4 | 	gpio7_16 |
| /sys/class/leds/led_P9_19 | 	P9_19 | 	gpio0_13 | 	gpio7_3 |
| /sys/class/leds/led_P9_20 | 	P9_20 | 	gpio0_12 | 	gpio7_4 |
| /sys/class/leds/led_P9_21 | 	P9_21 | 	gpio0_3 | 	gpio3_3 |
| /sys/class/leds/led_P9_22 | 	P9_22 | 	gpio0_2 | 	gpio6_19 |
| /sys/class/leds/led_P9_23 | 	P9_23 | 	gpio1_17 | 	gpio7_11 |
| /sys/class/leds/led_P9_24 | 	P9_24 | 	gpio0_15 | 	gpio6_15 |
| /sys/class/leds/led_P9_25 | 	P9_25 | 	gpio3_21 | 	gpio6_17 |
| /sys/class/leds/led_P9_26 | 	P9_26 | 	gpio0_14 | 	gpio6_14 |
| /sys/class/leds/led_P9_27 | 	P9_27 | 	gpio3_19 | 	gpio4_15 |
| /sys/class/leds/led_P9_28 | 	P9_28 | 	gpio3_17 | 	gpio4_17 |
| /sys/class/leds/led_P9_29 | 	P9_29 | 	gpio3_15 | 	gpio5_11 |
| /sys/class/leds/led_P9_30 | 	P9_30 | 	gpio3_16 | 	gpio5_12 |
| /sys/class/leds/led_P9_31 | 	P9_31 | 	gpio3_14 | 	gpio5_10 |
| /sys/class/leds/led_P9_41 | 	P9_41 | 	gpio0_20 | 	gpio6_20 |
| /sys/class/leds/led_P9_91 | 	P9_91 | 	gpio3_20 | 	❌ |
| /sys/class/leds/led_P9_42 | 	P9_42 | 	gpio0_7 | 	gpio4_18 |
| /sys/class/leds/led_P9_92 | 	P9_92 | 	gpio3_18 | 	❌ |
| /sys/class/leds/led_A15 | 	A15 | 	gpio0_19 | 	❌ | 