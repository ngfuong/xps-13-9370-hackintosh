# xps-13-9370-hackintosh (TBU)
![about-this-mac](https://scontent.xx.fbcdn.net/v/t1.15752-9/253739639_413584107078702_117812842799645645_n.png?_nc_cat=105&ccb=1-5&_nc_sid=aee45a&_nc_eui2=AeFc2mR8XJT6cTKQYSuj5osf3QLaFL--MfPdAtoUv74x813OzBQwdTlL-A_u3Pu2WJC7hHUreZsb39zv4kl8w3tG&_nc_ohc=KspzjeWhgKMAX8moQ8v&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=95a465ea6c0e6237ae769df4ac16c96b&oe=61AFF6DA)
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
* **CPU Power Management**: Performance balanced config generated with [CPUFriendFriend](https://github.com/corpnewt/CPUFriendFriend)
* **OpenCore Boot GUI & Chime**
* **Brightness slider**
* **Mapped Intel USB ports**: [USBMap Guide](https://github.com/corpnewt/USBMap)
* **Bluetooth**

# What's not working?
* XPS 13's dumb internal wifi card
* Unable to turn off Bluetooth

