# GPD P2 MAX Hackintosh

EFI files for hackintosh on the GPD P2 MAX, works on Catalina and Big Sur.
If you see anything that could be added or changed don't hesitate to make a pull request.

![Catalina with working Graphics Acceleration](/images/Catalina.jpeg)

## Basic Usage

1. Create a bootable Big Sur or Catalina bootable USB using this [tutorial](https://internet-install.gitbook.io/macos-internet-install/) but use my CLOVER folder at the point where you should configure CLOVER bootloader
2. Boot from this usb then install Big Sur/Catalina on a free partition of your drive
3. During first boot, after installing the OS, mount your EFI partition and place the CLOVER folder alongside other OSes bootloader
4. Reboot and change BIOS bootloader order to have clover bootloader as first entry
5. Open your config.plist and generate a new serial number [Tutorial here](https://hackintosher.com/forums/thread/generate-your-own-hackintosh-serial-number-board-serial-number-uuid-mlb-rom-in-clover.306/), If you use the `Clover Configurator` to generate directly, it will be more convenient.
6. Install additionals drivers.
7. Reboot and enjoy !

## What works

- Graphics Acceleration
- Bluetooth
- Brightness control
- Audio
- Power Management
- Battery Status
- USB and USB Mapping
- Keyboard
- Camera
- Sleep / Wake ( Black screen on Big Sur when wake up )
- TouchPad ( 20190919 Chinese keyboard firmware will cause problems, use the file driver inside touchpad_driver to downgrade, credits : @Gabe87 from insanelymac )
- TouchScreen
- Internal Wi-Fi Intel AC 7625

## What doesn't work

- Fingerprint Sensor

## How to use the internal Wi-Fi

Install  `HeliPort` to `/Applications`, run it and then set it boot automatically. Remove the original Wi-Fi icon from the tray.

The lastest Wi-Fi and Bluetooth driver: https://github.com/OpenIntelWireless

## Note

I removed

```
<key>framebuffer-fbmem</key>    
<data>AAAAAw==</data>    

<key>framebuffer-stolenmem</key>    
<data>AAAwAQ==</data>
```

in config.plist to support more higher resolution, such as 1440x900 HiDPI, 1680x1050 HiDPI.

So you shoud run:

```
setup_var_3 0x876 0x02
```

like this (https://github.com/Azkali/GPD-P2-MAX-Hackintosh/issues/16) to set the DVMT Pre-Allocated from 32M to 64M.

## Credits

@Gabe87 from insanelymac forums \
[Fewt's Hackintosh guide](https://fewt.gitbook.io/laptopguide/) \
[GPD for making the great P2 MAX](http://gpd.hk/)

### Special Mentions

Thanks to [@andreyakostov](https://github.com/andreyakostov) for his direct contributions and help throughout the project since the beginning ! \
[@lazd](https://github.com/lazd/VoodooI2CGoodix) for the Goodix TouchScreen driver \
[@THEDVIOUS1](https://github.com/THEDEVIOUS1) \
[@andot](https://github.com/andot)
