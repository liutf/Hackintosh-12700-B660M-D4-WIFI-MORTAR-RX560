# Hackintosh-12700-B660M D4 WIFI MORTAR-RX560 EFI

![](https://cdn.jsdelivr.net/gh/liutf/img-bed/img/20220722230937.png)

适用于 12700 + B660M迫击炮 WIFI DDR4 + AMD RX560 EFI 黑苹果引导文件

基于 OpenCore 引导，机型 MacPro 7,1，系统 MacOS 12.5

本 EFI 参考其他基于 12代 引导与查阅资料，去除不必要的驱动并更新到最新版本，大家请自行更换三码

本人也是小白，摸石头过河，仅供参考。希望大家有优化的能同步回传共享指导我，感谢！


# 本机配置

| 配置        | 型号                                                         |
| ----------- | ------------------------------------------------------------ |
| CPU         | 12th Gen Intel Core i7-12700                                 |
| 主板        | MSI MAG B660M MORTAR WiFi DDR4                               |
| 显卡        | AMD Radeon RX 560 Series ( 2 GB / 蓝宝石 )                   |
| 内存        | 32 GB ( 海盗船复仇者 DDR4 3200MHz 16GB x 2 )                 |
| SSD         | 西数 WDS100T1X0E-00AFY0 (黑盘 SN850) (固态硬盘) 1TB --MacOS12.5 |
|             | 西数 WD_BLACK SN770 500GB (固态硬盘) --Windows11             |
| 机箱        | 九州风神 玄冰40 3F                                           |
| 电源        | 鑫谷 AN750 750W                                              |
| CPU 风扇    | 利民 PA120 SE 塔式                                           |
| WiFi + 蓝牙 | 英特尔 Wi-Fi 6E AX211 160MHz                                 |
| 声卡        | 瑞昱  @ 英特尔 High Definition Audio 控制器                  |


# 使用情况
CPU：正常。Geekbench跑分测试，Single-Core Score：1847，Multi-Core Score：12293。

显卡：正常（免驱）

WiFi：正常

蓝牙：正常

USB2/3：正常

声卡：正常

节能三项：正常

睡眠：正常

唤醒：正常

<img width="1245" alt="image" src="https://user-images.githubusercontent.com/14069370/180410136-9150f61d-79f5-45b8-b468-5bfb7de7d1f1.png">

![image](https://user-images.githubusercontent.com/14069370/180410161-1af4aff5-353c-43b2-8a37-f89ea2a3b9d7.png)

![image](https://user-images.githubusercontent.com/14069370/180410175-eecce5da-d0a4-4d5d-9bdf-1ea1bfea74a5.png)

![image-20220724075018415](https://cdn.jsdelivr.net/gh/liutf/img-bed/img/image-20220724075018415.png)

![image-20220724074823912](https://cdn.jsdelivr.net/gh/liutf/img-bed/img/image-20220724074823912.png)



![image-20220724074944859](https://cdn.jsdelivr.net/gh/liutf/img-bed/img/image-20220724074944859.png)




# 避坑指南

### SSD

经真机测速 不支持 三星PM9A1、雷克沙NM800 状况为抹盘时卡在创建分区时或安装缓慢卡在重启安装阶段无限循环

金士顿 KC3000 有用户实测可以正常使用


# 其他说明

~~如果需要通过 OC 引导 Windows 请清除配置信息： Config—Misc—Security—scanpolicy 改为 0~~ 

已设置OC引导Windows（我两块SSD盘分别安装MacOS与Windows11）


# BIOS 配置

本引导适用于 B660M 迫击炮主板，主板BIOS需一下设置


### 禁用：
Onboard CNVi Module Control-Disable Integrated

快速开机

Intel VT-D

CFG锁定

Speed Select Technology


### 开启：
Re-Size BAR Support

SR-IOV Support

电源 / ERP ready

详细可参考：[B660M 迫击炮主板 BIOS设置](https://heipg.cn/tutorial/b660m-install-macos.html#BIOS-%E8%AE%BE%E7%BD%AE)





## 参考资料

[微星 MAG B660M MORTAR 实装 macOS Big Sur 11.6.7/Monterey 12.4 经验分享](https://heipg.cn/tutorial/b660m-install-macos.html)

[国光的黑苹果安装教程](https://apple.sqlsec.com/)



# 更新记录

2022-07-24

* USB定制
* 睡眠问题修复
* SetApfsTrimTimeout置为-1

2022-07-22 

* 升级OpenCore至0.8.2，更新驱动到最新版本
* 添加OpenCore引导页面Heikintosh主题

2022-04-20 

* 修正更新0.8后无法启动的问题，增加nvmefix驱动，缩小启动ui图标

2022-04-19

* 更新 OC 到 0.8.0 更新驱动到最新版本


2022-03-26
- 取消WG驱动注入(MacPro机型不需要该驱动)显卡跑分变高
- 引导默认隐藏工具，且不引导windows分区
- 加入gpu温度传感器，取消显卡注入信息
- SMBIOS信息改为主板注入（引导windows后显示正确主板信息）

2022-03-25

基础版本，基于 OC 0.7.9

