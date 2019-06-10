# Asrock deskmini 310 hackintosh

2019/05/27: 基于原作者的成果，更新 clover，替换 FakeSMC 为 VirtualSMC，清理了一些文件

2019/05/14: Upgrade to 10.14.15, everything is alright.

## Gears
CPU: Intel Coffee Lake i7-8700

RAM: Kingston DDR4-2666 8GBx2 (KHX2666C15S48G)

SSD for OS X: sm961 256g (SAMSUNG MZVPW256HEGL-00000)

SSD fro Windows: m5p 128g (PLEXTOR PX-128M5Pro)

HDD1: wd 1t (WDC WD10JPLX-00MBPT1)

WIFI/BT: `BCM943602CS` or `DW1560`/`BCM94352Z`

CPU cooler: NOCTUA NH L9i

## Important task
- Please keep BIOS in 3.x version
- After copied all kexts to system, please remerber to use tool - Kext Utility to rebuild cache.

## For BIOS 4.x
DSDT Patch

```code
comment: Fix RTC _STA bug (fix asrock new bios failed to boot)
Find: A00A9353 54415301
Replace: A00A910A FF0BFFFF
```

## Works
- [x] Ethernet/WIFI/Bluetooth/Audio/USB 2.0, 3.0(type-A, type-C)

- [x] DP/HDMI dual monitor output

- [x] Shutdown、Sleep

- [x] Graphics(Intel UHD 630)

## Issues
~~If you are using FCPX, system will hang/freeze in FCPX when you add some video effects. 
Please disable background rendering in FCPX first.
It's macOS 10.14.3 issue, someone report that 10.14.4 beta has already fixed this issue, let's wait the version release.(finger crossed!)~~

After upgraded to 10.14.4, FCPX is running smoothly, enable background rendering and everything is fine.

## Snapshot
![About](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/about.png)

![IGPU](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/IGPU.png)

![bluetooth](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/bluetooth.png)

![ethernet](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/ethernet.png)

![usb](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/usb.png)

![video_1](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/video_1.png)

## Dual monitor output - DP and HDMI
![video_2](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/dual_monitor1.png)

![video_3](https://github.com/liminghuang/asrock_deskmini310_hackintosh/raw/master/snapshot/dual_monitor2.png)


## Tools - Here are some tools you need...

Clover Configurator

MultiBeast

MaciASL

Kext Utility

IORegistryExplorer

Hackintool

Kext Updater

## Notes
After macOS installed done, please leave FakeSMC.kext only in /Library/Extensions and use Kext Updater tool to install other kexts again. Kext Updater will help you to manage what dictionary is good for kext driver to install.

*ps. I remove my serial number and others private info in SMBIOS, please refill those info by Clover first.

# Why I choose hackintosh? 
[My youtube link](https://youtu.be/d5WUizoIxy0) <-- Language is Mandarin
