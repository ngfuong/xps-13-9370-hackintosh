# Installation Guide
## Create install USB
Same as installing any OS, installing macOS requires an installation partition (USB/hard drive partition). Get started from the [vanilla guide USB Creation](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/).

If you use `macrecovery`, you'll get an online installer, which is not suitable for our hardware because:
1. No native Ethernet port
1. Wifi card is not compatible with macOS

So offline installer, how?
### Within macOS
You probably have to use Munki's [installinstallmacos](https://github.com/munki/macadmin-scripts) to obtain the `<OS-of-interest>.dmg`.

| ![Imgur](https://i.imgur.com/Dic5RVx.png) |
|:--:|
| *Mount the image then choose `Show Package Contents`*|


| ![Imgur](https://i.imgur.com/uwBUCJO.png) |
|:--:|
| *Execute file `createinstallmedia` with flag `--volume <partition-path>` to format the installer to our USB.* |

### Within Windows/Linux
Sadly Munki's magic installer does not work without macOS. My best bet is grabbing a lightweight macOS image (i.e Catalina), then create a Virtual Machine and follow the steps above.

## Setting up EFI partition
### Mount EFI
Next, use [MountEFI](https://github.com/corpnewt/MountEFI) to mount the EFI partition of our USB.

For Linux, use `lsblk` command to list all partition and `mount` command to mount the EFI partition. Alternatively for macOS, `diskutil list` and `mount` does the same thing as `lsblk` and `mount` in Linux.

### Collect files
There are multiple files required to make our hackintosh functional. Generally, they are categorized into three types and can be collected in the below order.
1. Base OpenCore files
1. Driver firmwares
1. Kexts
1. SSDTs

### 1. Base OpenCore files
An Opencore EFI partition needs to follow a folder structure. To get started, download the base EFI folder from [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/releases/) (DEBUG version recommended). Copy the `X64` folder to your our USB's mounted EFI partition.
>We need `X64` because our CPU architecture is x86-64.

Delete the unneccessary files in `EFI\OC\Drivers` and `EFI\OC\Tools`. After removing bloated files, the folder structure should be looking like this:
```
EFI (partition name)
├── EFI (folder)
│   ├── BOOT
│   │   └── BOOTx64.efi (required)
└───└── OC
    │   ├── ACPI
    │   ├── Drivers
    │   │   └── OpenRuntime.efi (required)
    │   ├── Kexts
    │   ├── OpenCore.efi (required)
    │   ├── Resources
    │   │   ├── Audio
    │   │   ├── Font
    │   │   ├── Image
    │   │   └── Label
    │   ├── Tools
    │   │   └── OpenShell.efi (required)
    └───└── config.plist (required)
 ```

 ### 2. Driver firmwares
 As the name suggests, the firmware `.efi` files must be placed inside `OC\Drivers`. The files we need are:
 * `OpenRuntime.efi` (added earlier)
 * `HfsPlus.efi` (required)
    * For reading HFS+ partition (i.e installer partition, recovery partition)
 * `OpenCanopy.efi` (optional)
    * For booting with cosmetic (can be added post-install)

If we plan to dual-boot Linux in the future, we also need `OpenLinuxBoot.efi` but it's story for [MULTIBOOT.md](MULTIBOOT.md).

### 3. Kext
Continue in [KEXTS.md](KEXTS.md).

### 4. SSDT
Conitnue in [SSDT.md](SSDT.md).

## Customize config.plist
TBD
