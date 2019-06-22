# Asrock deskmini 310 hackintosh

基于原作者的成果，更新 clover， ~~替换 FakeSMC 为 VirtualSMC，~~ 清理了一些文件

## 我的配置
CPU: Intel Coffee Lake i7-8700

内存: Kingston DDR4-2666 8GBx2 (KHX2666C15S48G)

SSD for OS X: wd sn750 500g (WDS500G3X0C-00SJG0)

SSD fro Windows: m5p 128g (PLEXTOR PX-128M5Pro)

HDD1: wd 1t (WDC WD10JPLX-00MBPT1)

WIFI/蓝牙: `BCM943602CS` or `DW1560`/`BCM94352Z`

散热器: NOCTUA NH L9i

## 备注

* 进安装器如果黑屏重新插拔视频线即可，安装完成后无需插拔。
* 配置内不含三码，请使用 Clover 配置器自行生成。如果正确生成的假三码不能使用 iMessage 等功能，换成你在 iPhone 上使用的 Apple ID 登陆。
* 请使用原版系统安装，安装后将 EFI 目录放置于 EFI 分区内即可，不要乱动系统分区。
* 唯一需要在系统分区操作的，是使用 clover 安装工具安装 “安装 RC scripts 到目标分区”，用来完善 nvram。
* 理论上任何版本的 bios 都可以，我已经加进去了华擎的补丁。这个补丁在华擎 z390 主板上工作良好。
* 我之前一直使用 `bcm94352z`(戴尔起的名字叫 `dw1560`)，完全够用，而且 win10 支持很好，linux 在驱动管理器里启用闭源驱动即可使用。后来换了 `bcm943602cs` 发现效果更好，但是 win10 需要安装苹果提供的 bootcamp 驱动，linux 还没试过。
* 我买到的这块 `bcm943602cs`（三天线）不知道什么来路，蓝牙居然是 4.2 的。
* 网上有提到 L9i 猫扇会压弯主板，其实不是风扇的问题，是 cpu 扣具太紧了。把 cpu 扣具上的螺丝适当拧松就不弯了（当然猫扇也别大力拧）。
* `FakeSMC` 很久没有更新了，所以我本来已经更换成了比较新的 `VirtualSMC` 的，但是最近 Clover 更新了之后唤醒变成开机，检查过后居然是 `VirtualSMC` 的问题，所以这个仓库又换回  `FakeSMC` 了。
* `i7-8700` 在这个机型上性能受供电限制。推荐换成 `i5-8500`。

![benchmark](https://raw.githubusercontent.com/xiaooloong/asrock_deskmini310_hackintosh/master/snapshot/benchmark.png)

## 感谢

* [liminghuang](https://github.com/liminghuang) 提供的[全套配置](https://github.com/liminghuang/asrock_deskmini310_hackintosh)
* [camgame](http://i.pcbeta.com/space-uid-535201.html) 提供的 [usb 补丁](http://bbs.pcbeta.com/forum.php?mod=redirect&goto=findpost&ptid=1799808&pid=48716684)