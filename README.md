# macOS Big Sur - Hackintosh
## Intel 10900k, Z490 Vision G, RX 6900XT

**Latest working macOS**: 11.4

**Current OpenCore**: 0.6.9

Complete hardware specs:
- Intel 10900k OC to 5.1GHz
- Gigabyte Z490 Vision G
- Noctua NH-D15 (with Thermal Grizzly Kryonaut) 
- AMD Radeon RX 6900 XT
- Fenvi T919
- 64GB RAM - 3200 MHz DDR4
- 500GB Kingston A2000 NVMe PCIe SSD (macOS Partition) + 500GB Kingston A2000 NVMe PCIe SSD (Windows Partition) + 4TB Samsung Evo 860 SATA SSD (shared with Windows, formatted as exFAT)

**SMBIOS**: iMac20,2

The system dual boots Windows 10

## Get it running
0. Make sure to update your BIOS, disable VT-d, disable CSM support and enable XHCI Hand-off (for Airdrop/Continuity/Sidecar)
1. Create an macOS Catalina/Big Sur USB-Installer Stick, install OpenCore and copy my EFI folder ([how?](https://github.com/SchmockLord/Hackintosh-Intel-i9-10900k-Gigabyte-Z490-Vision-D#installation-notes))
2. Generate a new serial number, motherboard id, ROM (that's your mobo's mac address without dots) and SMUUID (make sure serial number is **invalid** in order to iMessage/Facetime to work) ([how?](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html#platforminfo) + [this tool](https://mackie100projects.altervista.org/download-opencore-configurator/))
3. Boot the new macOS partition

## What works
- macOS Big Sur (probably Catalina too, use release v1.1 if it doesn't)
- WiFi and Bluetooth + Airdrop + Sidecar + Continuity (OOB thanks to Fenvi T919)
- Audio
- HDMI/DP (OOB thanks to 6900 XT)
- All USB ports
- 2.5Gbit Ethernet
- Everything iCloud related (Drive, iMessage, Facetime, unlock with Apple Watch, etc)
- Intel Quick Sync (if you enable IGPU in BIOS)
- Temperature monitoring for everything except GPU (no GPU temp support in VirtualSMC for navi and big navi cards)
- DRM content (Netflix, ATV+, Airplay 2 mirroring etc)
- Shutdown/Reboot/Update to newer macOS builds over time

## What doesn't work
- Sleep? Never got the chance to test it, my hackintosh is up 24/7

![alt text](https://i.imgur.com/NtHc8uK.jpg "neofetch")

## Kexts used:
- AppleALC (audio)
- Lilu + Whatevergreen (Audio helper, DRM support, IGPU helper)
- VirtualSMC + addons (you cannot boot without this + temperature support)
- FakePCIID (cpu support)
- FakePCIID_Intel_I225-V (ethernet support)

## Drivers used:
- OpenCanopy.efi (required by OpenCore)
- OpenRuntime.efi (required by OpenCore)
- HFSPlus (optional, make HFS drives discoverable in OpenCore bootloader if you want to use Mojave or older macOS versions)

## Thanks/Credits
- [SchmockLord](https://github.com/SchmockLord/Hackintosh-Intel-i9-10900k-Gigabyte-Z490-Vision-D)
- [samuel21119](https://github.com/samuel21119/Intel-i9-10900-Gigabyte-Z490-Vision-G-Hackintosh)
- tonymacx86
- insanelymac


**Fuck /r/Hackintosh for not allowing EFI sharing**
