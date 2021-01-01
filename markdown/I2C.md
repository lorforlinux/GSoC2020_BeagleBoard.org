---
layout: default
permalink: /I2C/
---

I2C bone bus nodes allow creating compatible overlays for BBBWl, BBB, & BBAI. For the definitions, you can see [bbai-bone-buses.dtsi#L388](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbai-bone-buses.dtsi#L388) & [bbb-bone-buses.dtsi#L403](https://github.com/lorforlinux/BeagleBoard-DeviceTrees/blob/97a6f0daa9eab09633a2064f68a53b107d6e3968/src/arm/bbai-bone-buses.dtsi#L388).

<div class="text-center text-dark border border-warning bg-dark">
    <a style="color:#ffc107; fill:#ffc107">
        Bone I2C reference chart
    </a>
</div>

| Bone bus | 	BBBWL/BBB | 	BBAI |	SCL |	SDA |	Overlay |
| /dev/bone/i2c/0 	| I2C0 | 	I2C1 | 	❌  | ❌ | On-board |
| /dev/bone/i2c/1 	| I2C1 | 	I2C5 | P9.17 	| P9.18 	|[BONE-I2C1.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_i2c/src/arm/BONE-I2C1.dts) |
| /dev/bone/i2c/2 	| I2C2 | 	I2C4 | P9.19 	| P9.20 	| [BONE-I2C2.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_i2c/src/arm/BONE-I2C2.dts) |
| /dev/bone/i2c/2a 	| I2C2 | 	N/A | P9.21 	| P9.22 	| [BONE-I2C2A.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_i2c/src/arm/BONE-I2C2A.dts) |
| /dev/bone/i2c/3 	| I2C1 | 	I2C3 | P9.24 	| P9.26 	| [BONE-I2C3.dts](https://github.com/lorforlinux/bb.org-overlays/blob/bone_i2c/src/arm/BONE-I2C3.dts) |