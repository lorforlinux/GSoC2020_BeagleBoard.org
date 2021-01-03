---
layout: default
permalink: /SPI/
---

Compatibility layer provides very easy to use SPI bone bus nodes that allows anybody to create compatible overlays for BBBWl, BBB, & BBAI. The format followed for these nodes is `bone_i2c_#`. For the definitions, you can see [bbai-bone-buses.dtsi#L406](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbai-bone-buses.dtsi#L406) & [bbb-bone-buses.dtsi#L423](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbb-bone-buses.dtsi#L423).

### Example Overlays:

|Overlay|
| :---: |
|[BONE-SPI0_0.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_spi/src/arm/BONE-SPI0_0.dts)|
|[BBAI-SPI0_1.dts](https://github.com/beagleboard/BeagleBoard-DeviceTrees/blob/v4.19.x-ti-overlays/src/arm/overlays/BBAI-SPI0_1.dts)|
|[BONE-SPI1_0.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_spi/src/arm/BONE-SPI1_0.dts)|
|[BONE-SPI1_1.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_spi/src/arm/BONE-SPI1_1.dts)|

<div class="text-center text-dark border border-warning bg-dark">
    <a style="color:#ffc107; fill:#ffc107">
        Bone SPI reference chart
    </a>
</div>

| Bone bus | 	BBBWL/BBB | 	BBAI | 	MOSI | 	MISO | 	CLK | 	CS |
| :--: | :--:          |    :--:      | :--: | :--: | :--:          |    :--:      |
| /dev/bone/spi/0.x | 	SPI0 |	SPI2 |	P9.18 | 	P9.21 |	P9.22 |	P9.17 (CS0) <br> P9.23 (CS1 - BBAI only)|
| /dev/bone/spi/1.x |	SPI1 |	SPI3 | 	P9.30 |	P9.29 |	P9.31 | P9.28 (CS0) <br> P9.42 (CS1) |