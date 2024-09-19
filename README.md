# xps-13-9370-hackintosh
<p align="center">
  <img src="https://i.imgur.com/KodBvLC.png" alt="neofetch output"/>
</p>

## Overview and Credits
* Grand kudos to the [vanilla OpenCore Guide](https://dortania.github.io/OpenCore-Install-Guide/) and QuantumShqipe's [OC 0.6.3 EFI Folder](https://github.com/QuantumShqipe/OpenCore-0.6.3-XPS-13-9370-BigSur)
* Laptop hardware information could be found at [this gist](https://gist.github.com/ngfuong/910a94c33bd650a20fe4913a2d57e547)
* **MacOS Version**:
  * Ventura 13.6 (currently using)
  * Big Sur 11.6 (deprecated)
* **OpenCore Version**: 1.0.0

# What's working?
* **SMBIOS**: MacBookPro14,1 or 14,2 (for Kaby Lake(U) 8th gen)
* **Audio**: AppleALC with ALC299
* **Graphics**: Patched Intel UHD 620
* **Wifi**: TENDA W311-MI USB Dongle with chris1111's [Big Sur Adapter](https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter) or Android USB tethering with [HoRNDIS](http://joshuawise.com/horndis)
* **Bluetooth**: [BlueToolFixUp](https://github.com/acidanthera/BrcmPatchRAM)
* **USB Ports**: Mapped in Windows with [USBToolBox](https://github.com/USBToolBox/tool)
  > Alternatively, use [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) during MacOS installation then map USB in MacOS using USBMap's [Guide](https://github.com/corpnewt/USBMap)

# What's not working?
* Sleep currently disabled
* XPS 13's dumb QCA6174 internal wifi card
* Thunderbolt ports
* Touch ID (of course)

# Guides
## Installation
TBD...
## Kext Info
### 1. AppleALC
Set `layout-id=22` according to layout but somehow there is no sound output. Gotta load `CodecCommander` kext to temporarily fix this.
### 1. CodecCommander
Since ALC299 (ALC3271) has problems with headphone output, use [KNNSpeed's guide](https://www.tonymacx86.com/threads/guide-dell-xps-15-9560-4k-touch-1tb-ssd-32gb-ram-100-adobergb.224486/page-9#post-1539760) to install `Hda Verb` and `Jack Fix` to correct this.
If you cannot `cp -R` into `/usr/bin` because of `read-only filesystems`, `cp` into `/usr/local/bin` instead.
### 2. NVMEFix 
Currently not used because drive is Samsung T5/WD SN770. If you use a non-Apple NVME, enable this.
### 3. SMC Kexts
These SMC Kexts is compatible:
* VirtualSMC
* SMCBatteryManager
* SMCProcessor
* SMCLightSensor
* SMCDellSensors
* SMCSuperIO
### 4. CPUFriend
Enable this kext after OS is installed. And disable this kext when OS is being upgraded. 
Remember to generate the CPUFriendDataProvider according to your performance preferences.
(CPUFriendDataProvider kext should appear after the CPUFriend kext)
### 5. BlueToolFixup
If your wifi+bluetooth combo card (Qualcomm) is non-native (non-Apple Broadcom, Intel, etc), use this kext.
**Do not use on macOS 11 or earlier.**
### 6. Ethernet
### TBD...



