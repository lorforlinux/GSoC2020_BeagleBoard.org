---
layout: default
permalink: /LEDs/
---

The compatibility layer comes with simple reference nodes for attaching LEDs to gpio pins. The format followed for these nodes is `led_P8_##`/`led_P9_##`. The `gpio-leds` driver is used by these reference nodes and allows users to easily create compatible led nodes in overlays for BBBWL, BBB, and BBAI. For the definitions, you can see [bbai-bone-buses.dtsi#L16](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbai-bone-buses.dtsi#L16) & [bbb-bone-buses.dtsi#L16](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbb-bone-buses.dtsi#L16).

