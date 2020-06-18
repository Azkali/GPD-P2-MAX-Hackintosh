# GPD P2 MAX 黑苹果

在 GPD P2 MAX 运行黑苹果所需要的 EFI 文件支持 Catalina 和 Mojave 两个系统。

如果你发现任何可以添加或变更的东西，请不要犹豫，赶紧提交一个 pull request。

![Catalina with working Graphics Acceleration](/images/Catalina_cn@2x.png)

## 基本用法

1. 参考 [教程](https://internet-install.gitbook.io/macos-internet-install/) 创建一个 Mojave 或 Catalina USB 安装启动盘，然后把启动盘中 EFI 分区 EFI 目录下的内容替换为本项目的 EFI 目录中的内容。
2. 使用该 USB 安装盘安装 Mojave/Catalina 到你驱动器的一个空闲分区上。
3. 安装完成后初次启动，挂载 EFI 分区，然后把 CLOVER 文件夹放到 EFI 分区的 EFI 分区中，如果你有多系统的话，不要把其他系统的启动目录和文件删掉。
4. 重启进入 BIOS，修改启动器顺序，把 CLOVER 的启动器设置为第一个。
5. 打开你的 config.plist 生成一个新的序列号。[教程在此](https://hackintosher.com/forums/thread/generate-your-own-hackintosh-serial-number-board-serial-number-uuid-mlb-rom-in-clover.306/)。另外补充一下，用 Clover Configurator 这个工具直接生成会更方便。
6. 安装附加驱动程序。
7. 重启之后就可以愉快的玩了。

### 附加驱动程序

[Wifi dongle driver](https://github.com/chris1111/Wireless-USB-Adapter-Clover)

## 哪些可以正常工作

- 图形加速
- 蓝牙
- 亮度控制
- 声卡/麦克风
- 电源管理
- 电池状态
- USB 和 USB 映射
- 键盘
- 摄像头
- 睡眠 / 唤醒
- 触摸板 ( 20190919 中文键盘固件会导致问题, 请在 Windows 下运行 touchpad_driver 文件夹中的固件驱动进行降级。credits : @Gabe87 from insanelymac )
- 触摸屏 ( 仅支持 Catalina )

## 哪些还不能工作

- 指纹识别传感器

## Work in progress

- 内置 Wi-Fi

## Credits

@Gabe87 from insanelymac forums \
[Fewt's Hackintosh guide](https://fewt.gitbook.io/laptopguide/) \
[GPD for making the great P2 MAX](http://gpd.hk/)

### Special Mentions

Thanks to [@andreyakostov](https://github.com/andreyakostov) for his direct contributions and help throughout the project since the beginning ! \
[@lazd](https://github.com/lazd/VoodooI2CGoodix) for the Goodix TouchScreen driver \
[@THEDVIOUS1](https://github.com/THEDEVIOUS1) \
[@andot](https://github.com/andot)
