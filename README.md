# xps-13-9370-hackintosh
| ![neofetch output.png](https://i.imgur.com/KodBvLC.png) | 
|:--:| 
| *“Cosmic Cliffs” by James Webb Space Telescope*|

# Overview
This repository is dedicated to providing resources for transforming a Dell XPS 9370 into a **partially** functional hackintosh.

It's recommended to:
1. Determine your hardware specs
2. Read the Opencore vanilla guide extensively
3. Make your own EFI (and debug if possible)
4. Only use this repo as a reference point
   
    > Remember that hardware specs can vary between device to device so it's best you avoid copy - paste.

# Specifications
<details>
<summary>Reveal Hardware Specs</summary>
<span markdown="1">
<ul>
<li>Laptop: Dell XPS 13 9370 | Model 0H0VG3</li>
<li>CPU: Intel Core i7-8550U Kaby Lake R 8th gen | @1.80GHz</li>
<li>Chipset Model:
      <ul>
      <li>SMBIOS 3.0.0 present</li>
      <li>Handle 0x0002, DMI type 2, 15 bytes</li>
      <li>Base Board Information</li>
      <li>Manufacturer: Dell Inc</li>
      <li>Product Name: 0H0VG3</li>
      <li>Version: A00</li>
      <li>Serial Number: /5KRB5M2/CN129637CQ001C/</li>
      </ul>
</li>
  <li>RAM: 8GB | 1867MHz</li>
  <li>Graphics Card: Intel UHD Graphics 620</li>
  <li>Wireless Interface (Wifi/BT Combo): Qualcomm Atheros | QCA6174A 802.11ac Wireless Network Adapter</li>
  <li>Audio Codec: HDA-Intel - HDA Intel PCH | Realtek ALC3271</li>
  <li>Hard Drive: WD SN770 PCIe</li>
  <li>Screen Resolution: 1920x1080~60GHz</li>
</ul>
</span>
</details>


Detailed hardware dump using AIDA64 can be found at [this file](hardware_dump.json).

* **macOS Version**:
  * Ventura 13.6 (currently using)
  * Big Sur 11.6 (deprecated)
* **OpenCore Version**: 1.0.0

## What's working?
* **SMBIOS**: MacBookPro14,1 or 14,2 (for Kaby Lake(U) 8th gen)
* **Audio**: AppleALC with ALC299
* **Graphics**: Patched Intel UHD 620
* **Wifi**: TENDA W311-MI USB Dongle with chris1111's [Big Sur Adapter](https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter) or Android USB tethering with [HoRNDIS](http://joshuawise.com/horndis)
* **Bluetooth**: [BlueToolFixUp](https://github.com/acidanthera/BrcmPatchRAM)
* **USB Ports**: Mapped in Windows with [USBToolBox](https://github.com/USBToolBox/tool)
  > Alternatively, use [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) during macOS installation then map USB in macOS using USBMap's [Guide](https://github.com/corpnewt/USBMap)

## What's not working?
* Sleep currently disabled
* XPS 13's dumb QCA6174A internal wifi card
* Thunderbolt ports
* Touch ID (of course)

# Installation
Go to [INSTALL.md](DOCS/INSTALL.md)

# Credits
* Dortania's [OpenCore Guide](https://dortania.github.io/OpenCore-Install-Guide/)
* RehabMan
* KNNSpeed's [Guide](https://www.tonymacx86.com/threads/guide-dell-xps-15-9560-4k-touch-1tb-ssd-32gb-ram-100-adobergb.224486/page-9#post-1539760)
* QuantumShqipe's [OC 0.6.3 EFI Folder](https://github.com/QuantumShqipe/OpenCore-0.6.3-XPS-13-9370-BigSur)


