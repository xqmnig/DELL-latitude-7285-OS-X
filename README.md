# DELL-latitude-7285-OS-X
# Dell Latitude 7285 HD615 iGPU CLOVER and Open Core

## Specifics

- CPU : Intel® Core™ i5-7Y57 Processor (6M Cache, up to 3.60 GHz)
- Graphics : Intel® HD Graphics 615
- Sound : Realtek ALC3253 (ALC225)
- Display : 12.3 Inch 2880 X 1920 (WUXGA+) 3:2 10 Points Multi Touch
- Memory : Micron LPDDR3 16GB 1867MHZ (8GB * 2 Dual Channel)
- SSD : PM971 NVEM Samsung 256GB (2230), TOSHIBA KXG60ZMV512G 512GB (2240) (WWAN Slot * 1)
- Wireless : BCM9435AZE(DW1820) (WLAN Slot * 1)
- Battery : 32WHr(Bluid in) + 22WHr(Keyboard) 


## BIOS/Clover Bootloader/macOS Version

- BIOS : 1.7.0
- Clover Bootloader : Above v5.0
- Open Core : 0.61
- macOS : 10.15.X


## BIOS Setup

- Load Optimized Defaults then set 
    1,settings-general-advanced boot Options clera all Uncheck
                      UEFI boot path always,excpet
              System configuration-stat operation ACHI
              Secure boot enable-disabled
              Intel software guard extensions-disabled
              Virtualization support-VT for Direct I/O clera Uncheck

- Use clover/tools/dvmt.efi set bios undisplay DVMT and MSR lock
  1,use "Setup_var 0x795 0x2" to set dvmt to 64mb
  2,use "Setup_var 0x4ed 0x0" to disable msr lock



## What Works

***Graphics/Display***
- Intel® HD Graphics 615 QE/CI, 2048MB vRam
- Type C DP 2 ports Video/Audio output Hot Swap(Open Core not work)
- Thunderbolt Display output(Open Core not work)
- Brightness control
- Sidecar

***Audio***
- Built-in speaker
- Built-in microphone
- Line input
- DP Audio Output

***Input***
- I2C touch screen Up to 5 points Gesture action (recognized as Magic Trackpad 2)
- PS2 Keyboard with Backlight
- Touchpad 
- Volume button,  power button(Sleep/Power Key)

***Power Management***
- CPU/Speed Step
- Battery
- Type C PD 2 Ports Charging, PowerShare

***USB, Storage***
- Full Size/Type C USB 2.0, 3.0 Hot Swap
- m.2 NVME 2230 1 Slot and m.2 NVME 2230(2242) 1 Slot
- Thunderbolt 3 (coolboot)
- Thunderbolt 3 Test with RX560 egpu and DELL WD15 TD15 dock

***Wireless Communication***
- iMessage/FaceTime/App Store
- Wi-Fi, Bluetooth, Airdrop, Sidecar, Continuity function


## Issues

- Changing the headphone jack connection state while in battery use and in sleep mode causes noise and output problems  
  To solve this problem, sleep and wake up again

- Clover Thunderbolt 3 hot swap works but kernel panic may occur when Thunderbolt 3 device is disconnected


- I2C front and rear camera (AVStream2500, OV5670, OV8858) not recognized


