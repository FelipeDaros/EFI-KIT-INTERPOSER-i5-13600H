# KIT interposer i5 13600H

![overview-12 3](./Geekbench.png)

# EFI Details
**Latest working macOS**: 14.3.1
<br>
**Current OpenCore**: 0.9.8
<br>
**Release date**: 19/02/2024

# Computer specifications
|Item|Description|
|-|:-------:|
|CPU|Intel(R) Core(TM) i5-13600H
|Memory|16GB DDR5 (16Gx1)|
|Storage|NVMe ADATA XPG GAMING 512GB|
|GPU|RADEON RX 6600
|Ethernet|Intel's AND Realtek's 2.5Gb Ethernet.

# BIOS Settings

### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- VT-d (can be enabled if you set `DisableIoMapper` to YES)
- Compatibility Support Module (CSM).
- Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
    - This must be off, if you can't find the option then **`ENABLE`** `AppleXcpmCfgLock`. 
    - Your hack will not boot with `CFG-Lock` enabled.

### Enable
- VT-x
- Above 4G decoding. 
    - This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
    - Do not have both this option and `npci` on `boot-args` enabled at the same time.
    - When enabling Above4G, Resizable BAR Support may become an available on some motherboards. Please ensure this is **`DISABLED`** instead of set to Auto.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- SATA Mode: AHCI
