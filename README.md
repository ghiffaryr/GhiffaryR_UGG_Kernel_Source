# GhiffaryR UGG Kernel Source Code

Device configuration for Xiaomi Redmi Note 5A Prime/Y1 (_ugg_)
=====================================================

Basic   | Spec Sheet
-------:|:-------------------------
CPU     | Octacore-core 1.4 GHz Cortex-A53
CHIPSET | Qualcomm MSM8940 Snapdragon 435
GPU     | Adreno 505
Memory  | 3/4 GB
Shipped Android Version | Android 7.1.2 with MIUI 8
Storage | 32/64 GB
MicroSD | Up to 256 GB (dedicated)
Battery | 3080 mAh (non-removable)
Dimensions | 153 x 76.2 x 7.6 mm
Display | 720 x 1280 pixels, 5.5" IPS
Rear Camera  | 13.0 MP, LED flash
Front Camera | 16.0 MP
Release Date | November 2017

![Xiaomi Redmi Note 5A / Y1 Prime](https://fdn2.gsmarena.com/vv/pics/xiaomi/xiaomi-redmi-note-5a-1.jpg "Xiaomi Redmi Note 5A/Y1 Prime")

## How to Compile
```
$ git clone <github tree source>.git -g <branch>
$ export CROSS_COMPILE=$(pwd)/bin/aarch64-linux-gnu-
$ export ARCH=arm64 && export SUBARCH=arm64
$ make clean
$ make mrproper
$ mkdir Out
$ make O=Out ugg_defconfig
$ make O=Out -j$(nproc --all)
```

## Frequencies Table
```
hex //dec

CPU-clock calculation
19200000, 1
clock, clock source
to get clock eg: 19200000 * 73 = 1401000000 Hz

GPU-clock calculation
clock = clock source / 2
to get clock eg: 1000000000 / 2 = 500000000 Hz

CPU-clock  //Hz
0xEE09800  //249600000
0x16E36000 //384000000
0x192D5000 //422400000
0x1EE62800 //518400000
0x26E8F000 //652800000
0x2DC6C000 //768000000
0x3010B000 //806400000
0x35C98800 //902400000
0x39387000 //960000000
0x3B826000 //998400000
0x413B3800 //1094400000
0x48190800 //1209600000
0x4A62F800 //1248000000
0x4B87F000 //1267200000
0x4CACE800 //1286400000
0x5140C800 //1363200000
0x53819040 //1401000000
0x56F9A000 //1459200000
0x59439000 //1497600000
0x5A688800 //1516800000
0x5CB27800 //1555200000
0x5DD77000 //1574400000
0x626B5000 //1651200000
0x65DA3800 //1708800000
0x6B931000 //1804800000

CPUfreq-table //KHz
0x3CF00  //249600
0x5DC00  //384000
0x67200  //422400
0x7E900  //518400
0x9F600  //652800
0xBB800  //768000
0xC4E00  //806400
0xDC500  //902400
0xEA600  //960000
0xF3C00  //998400
0x10B300 //1094400
0x127500 //1209600
0x130B00 //1248000
0x135600 //1267200
0x13A100 //1286400
0x14CD00 //1363200
0x1560A8 //1401000
0x164400 //1459200
0x16DA00 //1497600
0x172500 //1516800
0x17BB00 //1555200
0x180600 //1574400
0x193200 //1651200
0x1A1300 //1708800
0x1B8A00 //1804800

CPU-cci (Camera Control Interface)
0x17D78400 //400000000
0x1FCA0555 //533333333

CPU-bw (Bandwith)
0x301  //769 /*  100.8 MHz */ >,
0x64B  //1611 /*  211.2 MHz */ >,
0x84C  //2124 /*  278.4 MHz */ >,
0xB71  //2929 /*  384   MHz */ >,	/* SVS	*/
0x1005 //4101 /*  537.6 MHz */ >,
0x1098 //4248 /*  556.8 MHz */ >,
0x13BD //5053 /*  662.4 MHz */ >,	/* SVS+	 */
0x1650 //5712 /*  748.8 MHz */ >,     /* NOM   */
0x1808 //6152 /*  806.4 MHz */ >,     /* NOM+  */
0x1B77 //7031 /*  921.6 MHz */ >;     /* TURBO */

CCI-cpufreq
cpu-to-dev-map-4
0x61A80 //400000
0x82355 //533333

GPU-clock        //Hz
0x26BE3680 //650000000 got artifact
0x2540BE40 //625000000 got artifact
0x24F47300 //620000000
0x24A827C0 //615000000 got artifact
0x23C34600 //600000000
0x2245CDC0 //575000000
0x20C85580 //550000000
0x1DCD6500 //500000000
0x1C4FECC0 //475000000
0x1AD27480 //450000000
0x17D78400 //400000000
0x165A0BC0 //375000000
0x1312D000 //320000000
0x11E1A300 //300000000
0xE4E1C00  //240000000
0xCDFE600  //216000000
0x9896800  //160000000
0x124F800  //19200000
```

## Releases
```
GhiffaryR Overclock Kernel v3 features :
• Big cluster CPU overclock up to 1.65 Ghz
• Little cluster CPU overclock up to 1.38 Ghz
• GPU overclock up to 600 Mhz
• GPU underclock down to 160 Mhz
• Buswidth improvements to 16/32 bits
• Display refresh rate overclock to 65 Hz
• Enabled double tap to wake
What changed?
• Reboot recovery fixed

GhiffaryR Overclock Kernel v4-r2 features :
• Big cluster CPU overclock up to 1.65 Ghz
• Little cluster CPU overclock up to 1.38 Ghz
• GPU overclock up to 600 Mhz
• GPU underclock down to 160 Mhz
• Buswidth improvements to 16/32 bits
• Display refresh rate overclock to 65 Hz
• Enabled double tap to wake
• Fast charging up to 2400 mA
• USB fast charging up to 900 mA
What changed?
• Cooler temperature
• Reduced NOM+ and TURBO GPU clock speed, but keep SUPER TURBO clock @600 mhz

GhiffaryR Overclock Kernel v5-r4 features :
• GPU overclock up to 550 Mhz
• GPU underclock down to 160 Mhz
• Buswidth improvements to 16/32 bits
• Display refresh rate overclock to 65 Hz
• Enabled double tap to wake
• Fast charging up to 2400 mA
• USB fast charging up to 900 mA
What changed?
• SUPER TURBO GPU @550 Mhz clock variant
```