# GPD P2 MAX Hackintosh

Hackintosh EFI files for the GPD P2 MAX.
If you see anything that could be added or changed don't hesitate to make a pull request or open an issue.

![Catalina with working Graphics Acceleration](/images/Catalina.jpeg)

## Basic Usage

1. Create a bootable Big Sur bootable USB using this [tutorial](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) but use the provided EFI folder instead of configuring it on your own
2. Boot from the freshly created USB then install Big Sur on a free partition of your drive
3. During first boot, after installing the OS, mount your EFI partition and place the EFI folder content alongside other OSes bootloader
4. Reboot and change BIOS bootloader order to have OpenCore bootloader as first entry
5. Generate a new SMBIOS using CorpNewt's [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
6. Reboot and enjoy !

## What works

- Battery Status
- USB and USB Mapping
- Keyboard
- Camera
- Sleep / Wake
- TouchPad ( 20190919 Chinese keyboard firmware will cause problems, use the file driver inside touchpad_driver to downgrade, credits : @Gabe87 from insanelymac )
- Internal Wi-Fi Intel AC 7625

## What doesn't work

- Fingerprint Sensor
- TouchScreen - **Catalina only !**
- Graphics Acceleration
- Bluetooth
- Brightness control
- Audio
- Power Management

## Credits

@Gabe87 from insanelymac forums \
[Dortania Hackintosh guide](https://dortania.github.io/) \
[GPD for making the great P2 MAX](http://gpd.hk/)

### Special Mentions

Thanks to [@andreyakostov](https://github.com/andreyakostov) for his direct contributions and help throughout the project since the beginning ! \
[@lazd](https://github.com/lazd/VoodooI2CGoodix) for the Goodix TouchScreen driver \
[@THEDVIOUS1](https://github.com/THEDEVIOUS1) \
[@andot](https://github.com/andot) for his contribution to this repository \
[@corpnewt](https://github.com/corpnewt) for his awesome work in the community \
[@Dajokeisonu](https://github.com/Dajokeisonu) for his help with setting up this OpenCore build
