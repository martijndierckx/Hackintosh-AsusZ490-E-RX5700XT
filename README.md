# Hackintosh-AsusZ490-E-RX5700XT

Hi everyone,

I have successfully installed MacOS Catalina 10.15.7 on a ASUS Z490-E.

You can find my EFI folder in this repository.

**Current Bootloader: OpenCore 0.6.3**

# Hardware
- Intel i9-10900k
- ASUS Z490-E:
	- Audio: Realtek ALCS1220A
	- 2.5Gbit Ethernet: Intel I225-V
	- Two USB-C/Thunderbolt 3 ports
- RAM: 32GB Corsair Vengeance LPX 3200Mhz CL16
- GPU: Sapphire Radeon RX 5700 XT NITRO+
- Wifi/BT: BCM94360CD
- Disks: 2 x 970 Plus NVMe SSD (One for OSX and One for Windows 10)

# Working
- [x] **Tested with macOS Catalina 10.15.7**
- [x] **Wifi and Bluetooth** (via BCM94360CD using a MQUPIN fenvi T919 Wireless Card). Replacing the onboard Intel WiFi-card doesn't work. See details below. And the [itlwm](https://github.com/OpenIntelWireless/itlwm) drivers do not seem stable for the moment.
- [x] **Audio**: Realtek ALCS1220A
- [x] **USB**: Have not invested much time myself. Just copied what was available for the Z490-P motherboard which seems to work.
- [x] **Thunderbolt 3**: Not using, so I didn't invest time in it.
- [x] **2.5Gbit Ethernet (Intel I225-V)**
- [x] **Brightness control over Displayport**: Using 2 mediakey tweaks in Opencore and this nice [NativeDisplayBrightness](https://github.com/Bensge/NativeDisplayBrightness) tool.
- [x] **GUI picker with custom icons**
- [x] **Sleep/Wake** 
- [x] **Shutdown**
- [x] **Restart**

# Not working so far
- [ ] **iGPU UHD630 Compute**: I can get my IGPU to show up when enabling IGPU multimonitor in the BIOS, but I'm not able to do any benchmarks on it. Geekbench doesn't allow to select the IGPU, so something is wrong. Hints are appreciated :-).

# Credits
Thanks for your support :) Your help was crucial for my build.
- [SchmockLord](https://github.com/SchmockLord/Hackintosh-Intel-i9-10900k-Gigabyte-Z490-Vision-D) for the basis of this setup
- [Dortania](https://github.com/dortania) for this great OpenCore Desktop Guide
- [headkaze](https://github.com/headkaze) for Hackintool and our productive conversations :)
- [Acidanthera](https://github.com/acidanthera) for too many things to mention each
- [RehabMan](https://github.com/RehabMan) for too many things to mention each
- [OpenCore project](https://github.com/OpenCorePkg) for this great bootloader