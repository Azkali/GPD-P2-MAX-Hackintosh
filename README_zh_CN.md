# GPD P2 MAX 黑苹果

在 GPD P2 MAX 运行黑苹果所需要的 EFI 文件支持 Catalina 和 BigSur 两个系统。

如果你发现任何可以添加或变更的东西，请不要犹豫，赶紧提交一个 pull request。

![Catalina with working Graphics Acceleration](/images/BigSur@2x.jpg)

## 基本用法

1. 参考 [教程](https://internet-install.gitbook.io/macos-internet-install/) 创建一个 BigSur 或 Catalina USB 安装启动盘，然后把启动盘中 EFI 分区 EFI 目录下的内容替换为本项目的 EFI 目录中的内容。
2. 使用该 USB 安装盘安装 BigSur/Catalina 到你驱动器的一个空闲分区上。
3. 安装完成后初次启动，挂载 EFI 分区，然后把 CLOVER 文件夹放到 EFI 分区的 EFI 分区中，如果你有多系统的话，不要把其他系统的启动目录和文件删掉。
4. 重启进入 BIOS，修改启动器顺序，把 CLOVER 的启动器设置为第一个。
5. 打开你的 config.plist 生成一个新的序列号。[教程在此](https://hackintosher.com/forums/thread/generate-your-own-hackintosh-serial-number-board-serial-number-uuid-mlb-rom-in-clover.306/)。另外补充一下，用 Clover Configurator 这个工具直接生成会更方便。
6. 安装附加驱动程序。
7. 重启之后就可以愉快的玩了。

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
- 睡眠 / 唤醒（Big Sur 有唤醒黑屏问题）
- 触摸板 ( 20190919 中文键盘固件会导致问题, 请在 Windows 下运行 touchpad_driver 文件夹中的固件驱动进行降级。credits : @Gabe87 from insanelymac )
- 触摸屏
- 内置 Wi-Fi Intel AC 7625

## 哪些还不能工作

- 指纹识别传感器

## 如何使用内置 Wi-Fi

安装 wifi 目录下的 HeliPort，然后设置为开机启动就可以了。

最新的 Wi-Fi 和蓝牙驱动： https://github.com/OpenIntelWireless

## 开机之后循环启动怎么解决

新的 config.plist 中移除了下面几行代码：

```xml
<key>framebuffer-fbmem</key>    
<data>AAAAAw==</data>    

<key>framebuffer-stolenmem</key>    
<data>AAAwAQ==</data>
```

目的是为了让内建显示屏支持更高的分辨率，例如：1440x900 HiDPI，1680x1050 HiDPI（但是需要使用专门的分辨率设置软件来设置，例如：SwitchResX）。

但是因为去掉了这两行代码，而默认的 DVMT Pre-Allocated 只有 32M，所以会导致开机时不断重启，解决方法是参考：https://github.com/Azkali/GPD-P2-MAX-Hackintosh/issues/16 中的方法，执行：

```
setup_var_3 0x876 0x02
```

将 DVMT Pre-Allocated 的设置改为 64M，就可以解决这个问题了。

## Credits

@Gabe87 from insanelymac forums \
[Fewt's Hackintosh guide](https://fewt.gitbook.io/laptopguide/) \
[GPD for making the great P2 MAX](http://gpd.hk/)

### Special Mentions

Thanks to [@andreyakostov](https://github.com/andreyakostov) for his direct contributions and help throughout the project since the beginning ! \
[@lazd](https://github.com/lazd/VoodooI2CGoodix) for the Goodix TouchScreen driver \
[@THEDVIOUS1](https://github.com/THEDEVIOUS1) \
[@andot](https://github.com/andot)
