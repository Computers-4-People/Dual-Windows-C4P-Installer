# 💿 Dual Windows C4P Setup

![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%26%2011-blue?style=flat-square)
![Made For](https://img.shields.io/badge/Made%20for-Laptop%20Refurbishment-lightgrey?style=flat-square)
![Status](https://img.shields.io/badge/Status-Stable-brightgreen?style=flat-square)

The **Dual Windows C4P Installer** is a custom-built Windows ISO that includes both **Windows 10** and **Windows 11** in a single setup. It’s designed for IT technicians, nonprofits, and refurbishers to streamline deployment, quality assurance, and donation readiness using automation, pre-installed tools, and smart configuration.

> 🛠️ Made with: NTLite, Batch & PowerShell scripting

---

## 💡 Key Features

- ✅ **Dual OS Support**: Pick Windows 10 or 11 during install
- ⚡ **Unattended Setup**: Includes apps, branding, network config, and diagnostics
- 🛠️ **Integrated Diagnostics**: C4P Pre/Post Setup Tools built-in
- 🎨 **Custom C4P Theme**: Wallpaper, icons, and color tweaks
- 🧼 **Automatic Clean-Up**: Prepares device for donation after diagnostics

---
## 🛠️ Requirements

All required files can be downloaded from this shared folder:  
📁 **[Download Folder (Google Drive)](https://drive.google.com/drive/folders/1fN7cxLbytQFPDvWiehK49wI6SdyHUXGc)**

### Folder Contents:

| File/Folder                            | Description                                                                 |
|----------------------------------------|-----------------------------------------------------------------------------|
| `ventoy-1.0.97/`                       | 🧰 Ventoy 1.0.97 installer folder                                          |
| `ventoy/`                              | 🎨 C4P Ventoy theme folder                                                 |
| `BitRaser Drive Eraser 3.0.0.7.iso`    | 🧹 BitRaser drive erasure tool with secure wiping standards                |
| `Dual Windows C4P Setup x64.iso`       | 💿 Dual Windows ISO with Windows 10 Pro + 11 Pro                           |
|                                        | 💿 Pre-configured + Windows CU Updates manually integrated monthly         |
|                                        | 🚀 Silently installs: Chrome, Edge, Edge WebView2, Visual C++ Redists      |
|                                        | 🚀 System tweaks: disables password expiration, auto-connects to C4P WiFi  |
|                                        | 🚀 Automated theming (wallpapers, desktop icons, branding, accent colors)  |
|                                        | 🚀 Integrates C4P Pre-Setup Diagnostics on first boot                      |

- 🧊 USB (16GB or larger)
---

## 🚀 Setup Guide

### 🧰 Part 1: Create the Bootable USB

1. In the `ventoy-1.0.97` folder, run `Ventoy2Disk.exe` as **Administrator**
   
2. Option → Uncheck `Secure Boot support`
   
3. Option → Partition style → `GPT`
   
4. Option → Partition Configuration → `exFAT` or `NTFS`
   
5. Insert USB → Select it in the drop down → Click **Install**
    
6. Copy the following to the **root of the USB**:
   - `Dual Windows C4P Setup x64.iso`
   - `BitRaser Drive Eraser 3.0.0.7.iso`
   - `ventoy` folder (C4P theme)

7. To do this for multiple USB drives, repeat step 5.
   
---

### 🔧 Part 2: Configure the BIOS

1. Reboot the device and enter BIOS:
   - HP: `Esc` or `F10`
   - Dell: `F2`
   - Lenovo: `F1` or `Fn+F2`
   - Acer/ASUS: `F2` or `Del`
   - Surface: Hold `Volume Up` + `Power`

2. Change these settings:
   - SATA Mode → `AHCI`
   - Secure Boot → `Disabled`
   - Boot Mode → `UEFI`
   - Save and exit

---

### 💻 Part 3: Boot the Device

- **Surface Devices**:  
  In BIOS → Boot Config → Swipe USB left → Tap **Exit and Continue**

- **Other Devices**:  
  Use Boot Menu (e.g., `F12`, `Esc`, `F8`) → Select your USB

---

### 🧹 Part 4: Wipe Drives with BitRaser

1. From Ventoy menu, launch `BitRaser Drive Eraser 3.0.0.7.iso`

2. Choose **BitRaser - Safe Mode**

3. Verify licenses show in the bottom right corner (WiFi must be connected, if not, click the gear in the top right corner and connect)
4. Select drive(s) to erase (⚠️**NEVER select the USB**⚠️)

5. Fill out required fields:
   - Technician Name (C4P staff only)
   - C4P Barcode (Asset Tag)
   - Donor ID (from Zoho Creator)

6. Click **Erase** → Confirm prompts  
   *(SED Drives: Click Erase → Close → Confirm)*

---

### 💿 Part 5: Install Windows 10/11

1. Turn off the laptop and boot again. Using the previous boot menu key, boot back into the USB drive.

2. Select `Dual Windows C4P Setup x64.iso`

3. Choose **Boot in Normal Mode**. Use wimboot mode only as a fallback.

4. Choose OS based on CPU generation:
   - Intel 6th Gen and older ↓ or Ryzen 1000–2000 → 💻 Windows 10
   - Intel 7th Gen and newer ↑ or Ryzen 3000+ → 💻 Windows 11

5. Delete old partitions → Recreate as needed  
   - Prioritize SSD or lowest capacity drive
   - All drives must be initialized (no "unallocated" space)

---

### 🔍 Part 6: Finalize Refurbishment

1. During post-setup, wait for applications to finish installing during Post-Setup Tasks. You will then be met with the C4P Pre-Logon Diagnostics tool. Navigate the menus and press c to close when done.

2. When the desktop loads, wait for a message box that says:


**"SetUserFTA Personal Edition**


**Hi again! Thanks for using SetUserFTA Personal Edition.**

**Just a friendly reminder that this program is free, and showing this message every 10th run helps us keep it that way.**

**Thank you for your support!"**


→ and Click **OK**.

3. Let Windows Updates completely finish installing all updates.

4. Run **BatteryInfoView** → If health < 60%, mark device as not donatable. If health < 60%, continue.

5. Run `C4P-Diagnostics-Tool.exe` from desktop:
   - Press `0` to begin full diagnostic sequence
   - Follow all on-screen instructions
   - Use with physical C4P quality assurance checklist

6. Once diagnostics are done, there will be a Passed.txt file generated onto the desktop showing the diagnostics test results, technician name, asset tag, date, time, and system specifications.

7. ✅ Mark device as refurbished in **Zoho Creator**.

🎉 **Done!** Device is now tested, cleaned, and ready for donation.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).  
Windows operating systems and BitRaser are licensed separately.

---

## 🙌 Credits

Built and maintained by **Arnold Ssemuyaga**  
Made for the **Computers 4 People** refurbishment pipeline
