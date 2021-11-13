# xps-13-9370-hackintosh (TBU)
![about-this-mac](https://scontent.xx.fbcdn.net/v/t1.15752-9/253620568_940449133492409_6562313273770403349_n.png?_nc_cat=107&ccb=1-5&_nc_sid=aee45a&_nc_ohc=7hZoDE-XqqoAX9fjpTI&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=1c20fbd5f37ca8171dc5537ffd411fb5&oe=61B3DBC7)
* Big thanks to the [vanilla OpenCore Guide](https://dortania.github.io/OpenCore-Install-Guide/) and @QuantumShqipe's [OC 0.6.3 EFI Folder](https://github.com/QuantumShqipe/OpenCore-0.6.3-XPS-13-9370-BigSur)
* Laptop hardware information could be found at [this gist](https://gist.github.com/ngfuong/910a94c33bd650a20fe4913a2d57e547)
* **MacOS Version**: Big Sur 11.6
* **OC Version**: 0.7.5

# What's working? (almost everything)
* **Audio**: AppleALC with ALC299

  > ALC299 (ALC3271) has problems with headphone output.
  > 
  > According to [EliteMacx68's guide](https://elitemacx86.com/threads/audio-distortion-when-using-headphones-on-laptops-clover-opencore.185/), install `Hda Verb` and `Jack Fix` to correct this.
  > 
  > If you cannot `cp -R` into `/usr/bin` because of `read-only filesystems`, `cp` into `/usr/local/bin` instead.
* **Graphics**: Patched Intel UHD 620
* **Wifi USB Adapter**: TENDA W311-MI with [Big Sur Adapter](https://github.com/chris1111/Wireless-USB-Big-Sur-Adapter)
* **Bluetooth**
* **Mapped Thunderbolt ports**: [USBMap Guide](https://github.com/corpnewt/USBMap)
* **CPU Power Management**: Performance-balance kext generated with [CPUFriendFriend](https://github.com/corpnewt/CPUFriendFriend)
* **Brightness Slider**
* **OpenCore Boot GUI**
* **Sleep & Wake from Keyboard**


# What's not working?
* XPS 13's dumb internal wifi card
* Unable to turn off Bluetooth
* Trackpad randomly stops working

