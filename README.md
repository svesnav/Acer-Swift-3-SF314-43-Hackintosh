# Hackintosh Sonoma on Acer Swift 3 SF314‑43 (Ryzen 7 5700U)

This repository contains a working **EFI** configuration for running **macOS Sonoma (14.x)** on the **Acer Swift 3 SF314-43** with AMD Ryzen 7 5700U, using **OpenCore 1.0.5**.

---

## ✅ What Works

* Keyboard
* Touchpad
* All USB 3.0 ports & USB‑C
* Audio output
* Webcam
* Brightness and volume shortcut keys
* Integrated (Vega) GPU accelerated
* Wi‑Fi & Bluetooth (with Intel® Wi‑Fi 6 AX210 adapter)
* Android USB‑tethered modem (works via USB)

---

## ⚠️ What Does NOT Work

* Microphone (currently not functional)

---

## ⚙️ Important Notes

### VRAM / UMA Memory

To allocate at least **3 GB of unified memory (VRAM)** to the GPU, you must increase the UMA Frame Buffer Size using [Smokeless UMAF](https://github.com/DavidS95/Smokeless_UMAF).

### SMBIOS / Serial Data

You must change the values for **MLB**, **ROM**, **SystemSerialNumber**, and **UUID** in `config.plist` to unique values for your machine to enable Apple services (iMessage, App Store, iCloud).

### OpenCore Version

This setup is built on **OpenCore 1.0.5**. Be cautious when upgrading to avoid breaking compatibility.

### Config Setting

In OpenCore's `config.plist`, set `SecureBootModel` to `Disabled` (`Misc -> Security -> SecureBootModel`) for installation. After installing macOS, you can set `SecureBootModel` back to `Default` if needed.

---

## 🔗 Recommended Repositories & Tools

* [OpenCore Bootloader](https://github.com/acidanthera/OpenCorePkg) – official OpenCore repository and documentation
* [Smokeless UMAF](https://github.com/DavidS95/Smokeless_UMAF) – unlocks advanced memory allocation options in BIOS/UEFI

---

## 🚀 How to Prepare for Installation

1. Format a USB drive as **FAT32**, copy the `EFI` folder to its EFI partition.
2. Use [Smokeless UMAF](https://github.com/DavidS95/Smokeless_UMAF) to set **UMA Frame Buffer** to ≥ 3 GB.
3. In `config.plist`, replace MLB, ROM, SerialNumber, and UUID with your own unique values.
4. In `config.plist`, set `SecureBootModel` to `Disabled` (`Misc -> Security -> SecureBootModel`).

---

## 🚀 Installation

1. Boot from the prepared USB drive and install macOS Sonoma.
2. After installation, mount the EFI volume on the internal macOS drive and copy over the `EFI/OC` folder.
3. If you wish, set `SecureBootModel` back to `Default` in `config.plist`.
4. Reboot and use macOS Sonoma.

---

## ©️ Disclaimer

This configuration is shared for educational purposes. Use at your own risk. Ensure you comply with all legal requirements for running macOS on non‑Apple hardware.

---

## 📚 Further Reading

* [OpenCore Install Guide & Documentation](https://dortania.github.io/OpenCore-Install-Guide/) – for macOS Hackintosh best practices
