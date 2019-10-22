# GPD P2 MAX Hackintosh

EFI files for hackintosh on the GPD P2 MAX, works on Catalina and Mojave with BIOS v0.24.
If you see anything that could be added or changed don't hesitate to make a pull request.

![Catalina with working Graphics Acceleration](/images/Catalina.jpeg)

## Basic Usage

1. Create a bootable Mojave or Catalina bootable USB
2. Boot from this usb then install Mojave/Catalina on a free partition of your drive
3. During first boot, after installation place the CLOVER folder inside your EFI partition
4. Reboot and change Bios bootloader order to have clover bootloader as first option
5. Enjoy !

### Additional drivers

[Wifi dongle driver](https://github.com/chris1111/Wireless-USB-Adapter-Clover)

## What works

- Graphics Acceleration
- Bluetooth
- Brigthness control
- Audio
- Power Management
- Battery Status ( patch differs if you have a 1st batch or 2nd batch GPD P2 MAX, if you have the 2nd batch remove DSDT.aml, and rename DSDT_2.aml as DSDT.aml )
- USB
- Keyboard
- Camera
- Sleep / Wake

## Partially Working

- TouchPad ( 20190919 Chinese keyboard firmware will cause problems )

## What doesn't work

- USB Mapping ( it should work but it's not done yet, you can make a pull request to add it )
- TouchScreen
- Fingerprint Sensor
- Internal Wi-Fi ( Intel AC 7625 )

## Credits

[All users from the GPD Discord]()
[Fewr's Hackintosh guide](https://fewt.gitbook.io/laptopguide/)
[GPD for making the great P2 MAX](http://gpd.hk/)
