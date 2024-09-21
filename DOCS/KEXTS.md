
# Gathering Kexts
As the name suggests, the kext `.kext` files must be placed inside `OC\Kexts`.

## Universal kexts
The universally required kexts are listed below (without these, no system is bootable):
* [Lilu](https://github.com/acidanthera/Lilu/releases) (required)
    * For patching important kexts (VirtualSMC, WhateverGreen, AppleALC, etc)
* [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases) (required)
    * For emulating system management controller (SMC) chips on macs.

## VirtualSMC plugins
The below kexts are not required to boot but needed for hardware monitoring. These plugins are included in VirualSMC release.
* `SMCProcessor.kext`
    * For monitoring CPU temperatures
* `SMCSuperIO.kext`
    * For monitoring fan speed
* `SMCBatteryManager.kext`
    * For monitoring battery 
* `SMCDellSensors.kext`
    * Because our hardware is Dell laptop
* `SMCLightSensor.kext`
    * Still debugging. TBD.

## Graphics
* [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases) (required)
    * For graphics patching and fixing framebuffer (i.e fix HDMI)
    * Needed for all GPUs

## Audio
Audio is a hassle for our piece of hardware and should be needing more fix after OS installation.

For the moment, every non-legacy system will need:
* [AppleALC](https://github.com/acidanthera/AppleALC/releases) (required)
    * For patching Apple audio

* CodecCommander and VerbStub
    * For patching mic line-in
    * Refer to [POSTINSTALL.md](POSTINSTALL.md)

## Ethernet
* [NullEthernet](https://github.com/RehabMan/OS-X-Null-Ethernet)
    * For adding a fake ethernet device since we do not have native ethernet

## USB
It is highly recommended to map USB ports before OS installation. You will be needing:
* [USBToolBox](https://github.com/USBToolBox/kext) and [its tool](https://github.com/USBToolBox/tool)
    * For mapping USB ports within Windows or macOS
    * Refer to [USBMAP.md](USBMAP.md) for more information

However, if you decide to map USB later:
1. Use [USBInjectAll](https://github.com/Sniki/OS-X-USB-Inject-All/releases)
2. Set `XhciPortLimit` to `True` in `config.plist` to avoid port limit issues
3. Enable ACPI Patch `EHCI and XHCI ACPI renames` to avoid conflics with Apple's USB map (generally not needed because you will be using SMBIOS that do not need renames)

## Wifi and Bluetooth 
The wifi card (Qualcom Atheros QCA617A) is non-native to macOS. Unfortunately, there is currently no kext that supports this.

The card is also a bluetooth combo (appearing as Qualcom QCA61x4A). Fortunately this time, we can fix it using:
* [BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM/releases)
    * "Needed for all non-native Bluetooth cards", accoring to Dortania Guide

## Laptop Input
Our input devices include:
* I2C HID Device
* Standard PS/2 Keyboard
* Goodix fingerprint

Therefore, we must obtain the corresponding kext or else you have to use an external mouse and keyboard during setup.

* [VoodooPS2](https://github.com/acidanthera/VoodooPS2/releases), specifically VoodooPS2Controller (required)
    * For mapping PS2 keyboards and trackpads

* [VoodooI2C](https://github.com/VoodooI2C/VoodooI2C/releases) paired with VoodooI2CHID plugin (in VoodooI2C releases) (required)
    * For mapping I2C controllers and some USB devices

> FYI, any non-mac fingerprint devices probably will never be supported in the future.

## Miscellaneous
* [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys/releases)
    * For enabling `Fn`+`S` and `Fn`+`B` to adjust screen brightness

## Sanity Check
After populating your EFI folder, it should be something similar to this:
```
EFI (partition name)
├── EFI (folder)
│   ├── BOOT
│   │   └── BOOTx64.efi
└───└── OC
    │   ├── ACPI
    │   ├── Drivers
    │   │   ├── HfsPlus.efi
    │   │   └── OpenRuntime.efi
    │   ├── Kexts
    │   │   ├── AppleALC.kext
    │   │   ├── BlueToolFixup.kext
    │   │   ├── BrightnessKeys.kext
    │   │   ├── CodecCommander.kext
    │   │   ├── Lilu.kext
    │   │   ├── NullEthernet.kext
    │   │   ├── SMCBatteryManager.kext
    │   │   ├── SMCDellSensors.kext
    │   │   ├── SMCLightSensor.kext
    │   │   ├── SMCProcessor.kext
    │   │   ├── SMCSuperIO.kext
    │   │   ├── USBToolBox.kext
    │   │   ├── UTBMap.kext
    │   │   ├── VerbStub.kext
    │   │   ├── VirtualSMC.kext
    │   │   ├── VoodooI2C.kext
    │   │   ├── VoodooI2CHID.kext
    │   │   ├── VoodooPS2Controller.kext
    │   │   └── WhateverGreen.kext
    │   ├── OpenCore.efi
    │   ├── Resources
    │   ├── Tools
    └───└── config.plist
 ``` 