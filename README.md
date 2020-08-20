# b460m-martor-wifi
MSI B460M mortar 迫击炮 WIFI EFI
> 申明：配置主要来自网络各位分享者。由远景论坛&Github等。本人定制了B460M迫击炮的USB，支持原生94360CS2
> NGFF接口的网卡等。感谢各位分享者，我只是站在巨人肩膀上。

## 说明
当前配置使用稳定，USB已经定制，原生网卡的蓝牙和WI-FI都不需要驱动。USB3.0、双显卡等都OK。工作使用月余未发现问题。
休眠正常，没碰到过唤醒问题
所有配件都来自京东自营。网卡是淘宝购入。
### 温度
机器平时开发使用，正常负载使用温度在35-40度徘徊，编译在55-60度。R20跑分在78度左右
### 安装过程
- 准备安装U盘：参考OC官方配置，十分好用：[USB Creation](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#setting-up-opencore-s-efi-environment)，包含macOS、Windows、Linux的U盘制作。
- (重要)使用OpenCoreConfigurator打开我提供的EFI的OC/config.plist 重新生成SystemSerialNumber/SystemUUID/MLB等
- 开机配置主板各项配置，以及设置U盘UEFI启动顺序第一
- 插入U盘，选择U盘UEFI启动，进行安装系统
- 安装完成进入系统，成功!
### 其他
- boot-args 里 agdpmod=pikera 表示5000系显卡，非5000系显卡去掉这个
- 麦克风好像不能用
- USB定制是支持转接NGFF接口的网卡。不一定支持蓝牙外接主板的，需要自行再定制

## 硬件配置
| 名称 | 型号 |
| :---- | :---- |
| cpu | i7-10700 |
| 硅脂 | 利民 TF8 |
| 散热器 | 利民 TS120 plus 双风扇 |
| ram | 32gx2 3000MHz | 
| 主板 | MSI B460M Mortar WIFI | 
| graphis card | 华擎 Radeon RX 5500XT Challenger D 8G OC|
| SSD | SN750 500G M.2 |
| power | 海盗船 RMx 650 金牌全模组 |
| power line | 合金水冷 电源定制镀银线 |
| 机箱 | 乔思伯 C3-PLUS 银色|
| 无线网卡 | 黑苹果专用 BCM94360CS2+延长线转接卡 |
| 机箱风扇 | 12cmx4，14cmx1 |
| 显示器 | 27寸4Kx2 DPtoDP线x2 1080pHiDPI@60hz|

## 主板配置
- Fast Boot：关闭
- Secure Boot：关闭（默认关闭的）
- CFG lock 开启（重要）
- Intel SGX 如果有，关闭，默认关闭的
- Above 4G decoding 开启（重要）
- Hyper-Threading 开启（默认都开的）
- EHCI/XHCI Hand-off 开启 默认都开的）
- 显存: 64MB
- CPU风扇控制：默认主板只开启了CPU FAN自动控制，我打开了所有的自动控制，平时基本没有风扇声音
