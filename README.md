# Lenovo IdeaPad 500-14ISK (80NS) Hackintosh

This repository contains the EFI configuration files for running macOS on a Lenovo IdeaPad 500-14ISK. This build uses **OpenCore** and has been tested with **macOS Big Sur 11.4**.
---

## Hardware Specifications 💻

| Component | Model | Status |
| :--- | :--- | :--- |
| **CPU** | Intel Core i5-6200U (Skylake) | ✅ Working |
| **GPU** | Intel HD Graphics 520 | ✅ Working (QE/CI) |
| **RAM** | 8GB DDR3 1600MHz | ✅ Working |
| **Storage** | 256GB SATA SSD | ✅ Working |
| **Wi-Fi + BT** | Intel Dual Band Wireless-AC 3165 | ✅ Working |
| **Audio** | Realtek ALC235 | ✅ Working |
| **Trackpad**| Synaptics PS/2 Trackpad | ✅ Working |
| **Webcam** | Integrated Camera | ✅ Working |

---

## What's Working? ✅

* **Graphics Acceleration (QE/CI):** Intel HD 520 graphics work with full acceleration.
* **Audio:** Internal speakers, headphones, and microphone work correctly via AppleALC.
* **USB Ports:** All USB ports are mapped and functional.
* **Wi-Fi & Bluetooth:** Both work out of the box with the included kexts.
* **Keyboard & Trackpad:** Keyboard and multi-touch gestures on the trackpad are working.
* **Battery Management:** Battery status and percentage reporting are fully functional.
* **Sleep/Wake:** System sleeps and wakes correctly.
* **Webcam:** The integrated webcam is functional.
* **iServices (iMessage, FaceTime, iCloud):** Fully working with a valid SMBIOS.

## What's Not Working? ❌


* **SD Card Reader:** The built-in SD card reader is not functional.

---

## Installation 🛠️

### Prerequisites

1.  A USB drive (16GB or larger).
2.  Familiarity with the official [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/). This EFI is a supplement, not a replacement for the guide.

### Steps

1.  Download or clone this repository.
2.  **Generate a new SMBIOS:** This is a **CRITICAL** step to avoid conflicts with Apple's services.
    * Download and run the [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) script.
    * Use it to generate a new `SMBIOS` for `MacBookPro13,1`.
    * Open `config.plist` and navigate to `PlatformInfo > Generic`.
    * Update the `MLB`, `SystemSerialNumber`, and `SystemUUID` fields with your newly generated values.
3.  Copy the entire `EFI` folder from this repository to the EFI partition of your macOS installer USB.
4.  Follow the Dortania guide to create the bootable USB and perform the macOS installation.
5.  After installation, mount the EFI partition of your main drive and copy the `EFI` folder to it to make the system bootable without the USB.

---

## Disclaimer ⚠️

This EFI is provided for educational purposes only. I am not responsible for any damage to your hardware or data loss that may occur. Please proceed at your own risk. Note that running macOS on non-Apple hardware is a violation of Apple's End-User License Agreement (EULA).

---

## Credits & Acknowledgements 🙏

A huge thank you to the following individuals and teams for making this possible:
* [Acidanthera](https://github.com/acidanthera) for OpenCore and most of the essential kexts.
* [Dortania](https://github.com/dortania) for their incredibly detailed installation guides.
* The entire Hackintosh community for their constant support and development.
