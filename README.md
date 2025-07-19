# Dell-Latitude-7290-Opencore

This the the repository for the semi-functional OpenCore EFI using `OpenCore 1.0.1` aimed to run macOS Sonoma/Sequoia. Most of the features do work but some are not.

## System Specification
| Name          | Detail      |
|---------------|----------------------------------------------------------------------------------------------------------------------------|
| CPU           | 8th Generation Intel Core i3-i7 (i5-8250U)                                                                                 |
| GPU           | Intel KabyLake U & R (UHD 620)                                                                                             |
| Sound Codec   | Realtek ALC256                                                                                                             |
| Wireless Card | Intel Dual-Band Wireless-AC 8265 2x2 + Bluetooth 4.2                                                                       |
| RAM           | 8GB 2400MHz Single Channel                                                                                                 |
| Power         | 65W                                                                                                                        |
| IO            | HDMI 1.4<br> 3.5mm Audio port<br> Micro card reader (SD 4.0)<br> 2 x USB 3.1<br> Display Port over USB Type-C<br> RJ 45 (Gigabit)<br> Smartcard reader DC-in |

## What does not work
- Continuity features (required native Broadcom Wireless card, which the EFI's target system lacking)
- Sleep with AC plugged in, constantly waking up after sleep (`Wake on AC` option in BIOS disabled) (Sleep works normally in battery powered)
- External Display (BusID are not properly setting up, which is easily done using [this guide](https://dortania.github.io/OpenCore-Post-Install/gpu-patching/intel-patching/busid.html))
- "Boong" Boot chime (*really*?)

## Head-up
- `PlatformInfo` has been wiped (as `null` or `FFFFF`), you are required to use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) with `MacbookPro15,2` SMBIOS.
- This EFI is provided **as-is**, since then you must understand the OpenCore's inner working to use this EFI effectively, which means that I would be happy to ignore questions about "Why wont this work?".
- You can do whatever you want with this EFI (no credit, no "ily", just pure openness).
