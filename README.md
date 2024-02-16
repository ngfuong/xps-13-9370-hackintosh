# xps-13-9370-hackintosh
<p align="center">
  <img src="https://i.imgur.com/IzP7OIR.png" alt="about this mac"/>
</p>

* Big thanks to the [vanilla OpenCore Guide](https://dortania.github.io/OpenCore-Install-Guide/) and @QuantumShqipe's [OC 0.6.3 EFI Folder](https://github.com/QuantumShqipe/OpenCore-0.6.3-XPS-13-9370-BigSur)
* Laptop hardware information could be found at [this gist](https://gist.github.com/ngfuong/910a94c33bd650a20fe4913a2d57e547)
* **MacOS Version**:
  * Ventura 13.6
  * Big Sur 11.6
* **OpenCore Version**: 0.8.5

# What's working?
* **SMBIOS**: MacBookPro14,2 (closest to Kaby Lake(U) 8th gen)
* **Audio**: AppleALC with ALC299

  > ALC299 (ALC3271) has problems with headphone output.
  > 
  > According to [EliteMacx68's guide](https://elitemacx86.com/threads/audio-distortion-when-using-headphones-on-laptops-clover-opencore.185/), install `Hda Verb` and `Jack Fix` to correct this.
  > 
  > If you cannot `cp -R` into `/usr/bin` because of `read-only filesystems`, `cp` into `/usr/local/bin` instead.
* **Graphics**: Patched Intel UHD 620
* **Wifi USB Adapter**: TENDA W311-MI with [Big Sur Adapter](https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter) or Android USb tethering with [HoRNDIS](http://joshuawise.com/horndis)
* **Bluetooth**: [IntelBluetoothFirmware](https://openintelwireless.github.io/IntelBluetoothFirmware/)
* **Mapped Thunderbolt ports**: [USBMap Guide](https://github.com/corpnewt/USBMap)
* **CPU Power Management**: Performance-balance kext generated with [CPUFriendFriend](https://github.com/corpnewt/CPUFriendFriend)
* **Sleep & Wake from Keyboard (refrain from spamming)**


# What's not working?
* XPS 13's dumb QCA6174 internal wifi card
* Touch ID (of course)
