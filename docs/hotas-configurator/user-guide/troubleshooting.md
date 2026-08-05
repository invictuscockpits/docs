# Troubleshooting

This page covers common issues with the **Invictus HOTAS Configurator** and how to resolve them.

---

## 🚫 Device Not Detected
- **Firmware Requirement**: Invictus HOTAS Configurator requires firmware **v2.4.2.0 or later**.  
  - Devices shipped before **8/15/2025** may be running older firmware.  
  - These must be updated using the [Legacy Invictus VFT Configurator](https://invictuscockpits.com/pages/invictus-vft-configurator-software) before they can work with the current Configurator.  
- **Check USB cable** – must be a **data-capable** cable (not charge-only). If labeled *Charge & Sync*, it is usually suitable.  
- **Try another port** – connect directly to your PC, not through a hub.  
- **Drivers** – Windows will automatically install HID drivers; no manual drivers required.  

If still not detected:
- Press the **Reset** button on the board (if available).  

---

## 🔄 Device Disconnects Intermittently
- The Configurator continuously polls HID devices.
- If the connection drops:
  - Unplug and reconnect the USB cable.
  - Increase the **USB Exchange Rate** in the **Settings** tab (default = 5 ms).
  - Close other applications that may capture joystick input.
  - This is an annoyance with the GUI, but it does not actually affect the performance of the joystick. If you cannot resolve it, just ignore it as it does not cause any issues when actually flying. It is a software issue with the configurator that only affects certain boards. I have not been able to track it down. 

---

## ⚠️ Firmware Flashing Errors
During firmware updates, you may see one of these errors:

- **SIZE ERROR**  
  The `.bin` file is too large for the device’s memory.  
  → Use the correct firmware release for your board.  

- **CRC ERROR**  
  File checksum mismatch.  
  → Re-download the firmware and retry.  

- **ERASE ERROR**  
  Flash memory could not be erased.  
  → Retry flashing. If persistent, the board may be faulty.  

- **ERROR (666)**  
  Unknown error condition.  
  → Restart both the Configurator and the device.  

---

## 🎛️ Calibration Problems
- If axes do not center correctly:  
  - Ensure the **Center** box is checked in **Axes Settings**, and the value is set to **0**.  
  - Re-run calibration.  
  - Verify that **Invert** is not incorrectly selected.  

- If axes drift slightly off zero at rest despite calibration being correct:  
  - Enable **Hysteresis Compensation** on the affected axis (Axes → Extended Settings).  
  - Particularly effective for force-sensing Invictus grips, where the flexure doesn't always settle to the exact same ADC value after a release. The firmware captures the actual rest position and treats it as a dynamic zero, giving a clean 0 output with fine proportional response from rest.  

- If axis values update too slowly:  
  - Lower the **Filter** level or turn filtering off.  

- If force scaling options (digital/analog, 50/75/100%) behave incorrectly:  
  - Your device does not have factory force anchors (typical of units shipped before 8/15/2025).  
  - Use **Developer Mode** to set anchors manually.  

---

## 🛠️ Developer Mode Not Visible
- Press **Shift + D** to toggle Developer Mode on/off.  
- This reveals the Developer tab with anchor tools and diagnostics.  

---

## 🕹️ Legacy Configurator (For Older Devices)
If your device has firmware older than v2.4.2.0, it is not supported by the current Configurator.  

To update:  
1. Download the [Legacy Invictus VFT Configurator](https://invictuscockpits.com/pages/invictus-vft-configurator-software).  
2. Download the [Latest Firmware Release](https://github.com/invictuscockpits/invictus-ssc-firmware/releases/latest) (you will need the `.bin` file — e.g., `InvictusHOTASv2.4.2.8.bin`).  
3. In the legacy Configurator:  
   - Enter **Flasher Mode**.  
   - Select the `.bin` file and flash firmware.  
   - If successful, the device will appear in the Invictus HOTAS Configurator.  

If the device does not update and remains stuck on “Invictus VFT”:  
- Part of the firmware is corrupted and it cannot update via the legacy tool.  
- Options:  
  - **Erase and Reflash with ST-Link**: See [Reflashing Firmware](reflashing-firmware.md).  
  - **Send the board in for service**:  
    - **US Customers**: A prepaid return label will be provided. Ship only the control board.  
    - **International Customers**: In most cases, we will send a replacement board to avoid high shipping/tariff costs.  
  - **Send your complete device**: We will reflash and recalibrate it. This includes adding accurate persistent force anchors to your device.  Shipping costs both ways are your responsibility, but calibration and anchors will be included at no charge.  

---

## ✅ Summary
- Ensure firmware is v2.4.2.0 or later for the current Configurator.  
- Use the **Legacy Configurator** if your device is older.  
- Most issues are related to USB cables, ports, or outdated firmware.  
- If recovery is needed, follow the [Reflashing Firmware](reflashing-firmware.md) guide.  
- For unresolved issues, contact [Invictus Cockpit Systems Support](https://invictuscockpits.com).
