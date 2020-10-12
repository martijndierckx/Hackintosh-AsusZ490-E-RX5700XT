# Hackintosh-AsusZ490-E-RX5700XT

Hi everyone,

I have successfully installed MacOS Catalina 10.15.7 on a ASUS Z490-E.

You can find my EFI folder in this repository.

**Current Bootloader: OpenCore 0.6.2**

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

# Details

If you get an error within the installation saying something like "this installation is damaged" you can try this workaround: 
 Delete Installinfo.plist on the installer disk:
  - Open the "Install macOS Catalina" Disk
  - Right Click on the package "Install macOS Catalina"
  - Click on "Package Contents"
  - Then navigate to Contents > SharedSupport
  - Delete the Installlnfo.plist


## Post Istall

Once you have installed MacOS Catalina onto your hackintosh's drive you should repeat the same steps above of installing the EFI folder onto it's EFI-partition:

  - (Don't have two EFI partitions mounted at the same time since it can confuse things)
  - Mount the EFI-partition of your hackintosh's drive (ie of the drive you installed Catalina onto)
  - Replace the entire contents of this EFI-partition with the your specialized entire EFI folder (which includes your own unique serial numbers)

Now your hackintosh can boot without the USB install stick.

Then following the other sections below you might want to investigate a GUI boot menu, a boot chime, and other post install niceties. (See [dortania post install cosmetics](https://dortania.github.io/OpenCore-Post-Install/cosmetic/gui.html#opencore-beauty-treatment))

## Fixing Sleep/Wake 

In this section I want to show you how I setup my system so it sleeps and wakes just fine, but I don't tell you that you need exactly these settings to have a proper configuration.

I also had to use ```SSDT-Disable-CNVW.aml``` to disable the CNVi feature of the m.2 slot, where the onboard Intel Wifi 6 sits, because the CNVi device was constantly waking up my PC.


# Credits
Thanks for your support :) Your help was crucial for my build.
- [SchmockLord](https://github.com/SchmockLord/Hackintosh-Intel-i9-10900k-Gigabyte-Z490-Vision-D) for the basis of this setup
- [Dortania](https://github.com/dortania) for this great OpenCore Desktop Guide
- [headkaze](https://github.com/headkaze) for Hackintool and our productive conversations :)
- [Acidanthera](https://github.com/acidanthera) for too many things to mention each
- [RehabMan](https://github.com/RehabMan) for too many things to mention each
- [OpenCore project](https://github.com/OpenCorePkg) for this great bootloader