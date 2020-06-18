# GPD P2 MAX Hackintosh

EFI files for hackintosh on the GPD P2 MAX, works on Catalina and Mojave with BIOS v0.24.
If you see anything that could be added or changed don't hesitate to make a pull request.

![Catalina with working Graphics Acceleration](/images/Catalina.jpeg)

## Basic Usage

1. Create a bootable Mojave or Catalina bootable USB using this [tutorial](https://internet-install.gitbook.io/macos-internet-install/) but use my CLOVER folder at the point where you should configure CLOVER bootloader
2. Boot from this usb then install Mojave/Catalina on a free partition of your drive
3. During first boot, after installing the OS, mount your EFI partition and place the CLOVER folder alongside other OSes bootloader
4. Reboot and change BIOS bootloader order to have clover bootloader as first entry
5. Open your config.plist and generate a new serial number [Tutorial here](https://hackintosher.com/forums/thread/generate-your-own-hackintosh-serial-number-board-serial-number-uuid-mlb-rom-in-clover.306/)
6. Install additionals drivers
7. Reboot and enjoy !

### Additional drivers

[Wifi dongle driver](https://github.com/chris1111/Wireless-USB-Adapter-Clover)

## What works

- Graphics Acceleration
- Bluetooth
- Brigthness control ( if your BIOS version is 0.27 remove ACPI/patched/SSDT-PNLF.aml and rename SSDT-PNLF-0.27.aml to SSDT-PNLF.aml )
- Audio
- Power Management
- Battery Status
- USB and USB Mapping
- Keyboard
- Camera
- Sleep / Wake
- TouchPad ( 20190919 Chinese keyboard firmware will cause problems, use the file driver inside touchpad_driver to downgrade, credits : @Gabe87 from insanelymac )
- TouchScreen - **Catalina only !**

## What doesn't work

- Fingerprint Sensor

## Work in progress

- Internal Wi-Fi Intel AC 7625

## Credits

@Gabe87 from insanelymac forums \
[Fewt's Hackintosh guide](https://fewt.gitbook.io/laptopguide/) \
[GPD for making the great P2 MAX](http://gpd.hk/)

### Special Mentions

Thanks to [@andreyakostov](https://github.com/andreyakostov) for his direct contributions and help throughout the project since the beginning ! \
[@lazd](https://github.com/lazd/VoodooI2CGoodix) for the Goodix TouchScreen driver \
[@THEDVIOUS1](https://github.com/THEDEVIOUS1) \
[@andot](https://github.com/andot)
