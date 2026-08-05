# Overview

This page provides an overview of the tabs and options in the Invictus HOTAS Configurator.

---

## 🔌 Connection
- The Configurator automatically detects your Invictus HOTAS device when plugged in (firmware version **2.4.2.0 or later** required).  
- The status indicator shows:  
  - **Connected (green)** – device is recognized and ready.  
  - **Disconnected (red)** – no device detected.  
  - **Incompatible Firmware (yellow)** – firmware is older than v2.4.2.0.  

⚠️ On first connection, you will be prompted to **save your original settings**. Keep this safe, as it contains calibration data unique to your device.

---

## 📑 Pin Settings (Developer Mode Only)
- Assigns hardware functions to control board pins.  
- Supported boards:
  - Invictus HOTAS family of SSC/VFT control boards.  
- Pin mapping is **automatically populated** when you select your board from the **Board dropdown**.  
- End-users should not normally change pins.  

> ⚠️ Pin settings are a developer feature and should only be changed when explicitly instructed.

---

## 🎮 Buttons
- Maps **physical buttons** (wired to the grip or shift registers) to **logical joystick buttons** seen by Windows and simulators.
- Supports:
  - Normal buttons
  - POV hats (up to 4 POVs; Falcon BMS supports only one POV hat)

When Falcon BMS is selected from the **Simulator dropdown**, POV2–POV4 are automatically remapped to normal buttons.

---

## 🎚️ Axes Settings
- Used to calibrate and tune joystick axes.  
- Settings include:  
  - **Min / Center / Max** calibration values (force-based calibration for SSC/VFT devices).  
  - **Invert Axis** – reverses output direction if needed.  
  - **Filter** – smooths sensor noise.  
  - **Deadband** – defines a center range where small movements are ignored.  

If your device shipped **after 8/15/2025**, these values are preloaded from factory anchors and cannot normally be deleted.  
Devices shipped earlier may require you to set values manually.  

See the [Axes Settings](axes-settings.md) page for full details.

---

## 🔢 Shift Registers
- Configures external shift register chips for expanding button inputs.
- Displays configuration for:
  - **Latch, Clock, and Data pins** – Hardware connections for the shift register
  - **Shift register type** – Type of chip being used
  - **Registers count** – Number of chained shift registers
  - **Button count** – Total buttons connected through shift registers

> ⚠️ This tab is automatically populated when you select your grip from the dropdown. End-users should not normally need to modify these settings.

Shift registers allow grip manufacturers to connect more buttons than would otherwise be possible with direct pin connections.

---

## ⚙️ Settings
- Change **language** (English, Russian, Chinese, German, and more).
  - All UI elements, including firmware version, buttons, and developer features, translate correctly.
- Adjust **font size** and **USB exchange rate**.
- **Check for Software Updates** – retrieves latest GUI releases.
- **Check for Firmware Update** – checks for latest device firmware.
- **Firmware Flasher** – update device firmware directly from the Configurator. Includes an on-screen 4-step guide (Read Device Settings → Enter Flasher Mode → Flash Firmware → Write Device Settings) and a confirmation popup once flashing completes.
- **Restart Application** – restart the Configurator to apply changes.
- **About Page** – shows version, source links, and Invictus website.
- **Device Information** – displays model, serial number, manufacture date, and firmware version.

---

## 🛠️ Developer Mode
*(Hidden; for advanced use only)*  
- Enable by pressing **Shift + D**.
- Adds the **Developer tab**, where you can:
  - Read, write, lock, and unlock **Factory Force Anchors** (protected calibration data stored in flash).
  - Read and write **Device Info** (serial number, model number, manufacture date).
  - View diagnostic logs and debug data.

> ⚠️ Force anchors should only be modified if you have proper calibration equipment or are directed by Invictus support.
