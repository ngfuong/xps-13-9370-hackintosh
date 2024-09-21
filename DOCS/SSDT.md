# Gathering SSDT
TBD
## Sanity Check
After populating your EFI folder, it should be looking like this:
```
EFI (partition name)
├── EFI (folder)
│   ├── BOOT
│   │   └── BOOTx64.efi
└───└── OC
    │   ├── ACPI
    │   │   ├── SSDT-ALS0.aml
    │   │   ├── SSDT-EC-USBX.aml
    │   │   ├── SSDT-PLUG.aml
    │   │   ├── SSDT-PNLF.aml
    │   │   ├── SSDT-RMNE.aml
    │   │   └── SSDT-XOSI.aml
    │   ├── Drivers
    │   │   ├── HfsPlus.efi
    │   │   ├── OpenCanopy.efi
    │   │   ├── OpenLinuxBoot.efi
    │   │   └── OpenRuntime.efi
    │   ├── Kexts
    │   │   ├── AppleALC.kext
    │   │   ├── BlueToolFixup.kext
    │   │   ├── BrightnessKeys.kext
    │   │   ├── CodecCommander.kext
    │   │   ├── Lilu.kext
    │   │   ├── NullEthernet.kext
    │   │   ├── RtWlanU.kext
    │   │   ├── RtWlanU1827.kext
    │   │   ├── SMCBatteryManager.kext
    │   │   ├── SMCDellSensors.kext
    │   │   ├── SMCLightSensor.kext
    │   │   ├── SMCProcessor.kext
    │   │   ├── SMCSuperIO.kext
    │   │   ├── USBMap.kext
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
    │   │   ├── CleanNvram.efi
    │   │   ├── CsrUtil.efi
    │   │   └── GRUB Shell.efi
    └───└── config.plist
 ``` 