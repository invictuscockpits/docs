<img src="https://github.com/user-attachments/assets/d0188479-0202-4b78-a5e4-3c55c6b37e7a" width="1200">


# Developer Mode

The **Developer Mode** tab is a hidden section of the Invictus HOTAS Configurator.  
It is intended only for factory use and advanced users.  

⚠️ **Warning:** Misuse of Developer Mode can permanently change calibration data. Most users should never need to access this tab.

---

## 🔓 How to Access
- Hold **Shift + D** while the Configurator is open.  
- A new **Developer** tab will appear in the main window.  

---

## 🏷️ Factory Force Anchors

Force anchors are **baseline calibration values** stored in a protected flash page on the device.  
They represent the **raw axis values (ADC counts)** that correspond to specific physical force levels on the stick.  

- Anchors are **not erased** when firmware is updated.  
- Anchors are **persistent** across all settings changes.  
- Anchors ensure every axis has a **known reference point** for proper force scaling.  
- You can experiment with alternate anchors, but factory-set anchors are always the reference.  

---

## Devices with Factory-Set Anchors
- All Invictus HOTAS devices shipped **after 8/15/2025** include **factory-set force anchors**.  
- These are measured using calibrated equipment and should never be changed unless directed by Invictus support.  

> ⚠️ If you overwrite or lock factory anchors, you cannot restore them without returning the device for service. This is not covered under warranty.

---

## ✋ Anchor Actions
The Developer tab provides anchor-related actions:

- **Read Force Anchors** – Displays the current factory anchors stored on the device.
- **Write Force Anchors** – Replaces existing anchors with the values you enter in Developer Mode.
- **Lock Force Anchors** – Seals the anchors to prevent accidental modification.
  - Locked anchors cannot be modified until unlocked.
  - ⚠️ Only lock anchors if you are confident they are correct.
  - Locking should only be performed with accurate, verified measurements.
- **Unlock Force Anchors** – Removes the lock, allowing anchors to be modified again.
  - Use with caution; only unlock if you need to correct or recalibrate anchors.
- **Export Force Anchors** – Saves the current anchors to a JSON file.
  - ⚠️ **CRITICAL:** Anchors are unique to each individual device. Export them immediately after receiving a new device and store the file safely.
  - This backup is essential for recovery if anchors are accidentally overwritten or corrupted.
  - The exported file includes all anchor triplets (100%, 75%, 50% for each direction).
- **Import Force Anchors** – Loads anchors from a previously exported JSON file.
  - Allows restoring your device's backed-up anchors if they were lost or modified.
  - After importing, you must click **Write Force Anchors** to save them to the device.
  - ⚠️ Only import anchors that were originally exported from the same device.

---

## 📋 Device Information

The Developer tab also allows you to read and write **Device Info**, which includes:
- **Serial Number** – Unique identifier for your device
- **Model Number** – Product model designation
- **Manufacture Date** – Date of manufacture (YYYY-MM-DD format)

### Device Info Actions
- **Read Device Info** – Displays the current device information stored on the device.
- **Write Device Info** – Updates the device information with new values.
  - This information is stored in protected flash memory.
  - After writing, the UI automatically refreshes to show the new values.
  - ⚠️ Only modify if you are Invictus staff or directed by support.

Device info is persistent and not erased during firmware updates.

---

## 🔧 ADC PGA Settings

The Developer tab includes controls for the **Programmable Gain Amplifier (PGA)** settings for Gen 4 boards with I²C ADC sensors (ADS1115).

### What is PGA?
The PGA adjusts the input voltage range that the ADC can measure. Higher gain settings provide finer resolution but measure a smaller voltage range.

### PGA Gain Options
- **PGA 1** – ±6.144V range (lowest resolution)
- **PGA 2** – ±4.096V range
- **PGA 4** – ±2.048V range
- **PGA 8** – ±0.512V range (default for most axes)
- **PGA 16** – ±0.256V range (highest resolution, smallest range)

### Default Settings (Gen 4 Boards)
- **Channel 0 (Roll/X-axis)**: PGA 8 (±0.512V)
- **Channel 2 (Pitch/Y-axis)**: PGA 16 (±0.256V)

These defaults are optimized for strain gauge load cells and provide the best balance of resolution and range.

### PGA Actions
- **Read PGA Settings** – Displays the current PGA configuration for each ADC channel.
- **Write PGA Settings** – Updates the PGA values on the device.
  - ⚠️ Incorrect PGA settings can cause axes to clip or lose precision.
  - Only change if you are replacing sensors or directed by support.
  - Default values work for all standard Invictus installations.

---

## 🧮 Determining Force Anchor Values
If your device shipped **before 8/15/2025**, anchors may not be present. You can set your own values.

Anchors correspond to raw ADC values measured at specific percentages of maximum stick force:

- **100%** = full rated force  
- **75%** = approximately ¾ force  
- **50%** = approximately ½ force  

Force levels by direction:
- **Roll Left / Right** – 17 lbf  
- **Pitch Down** – 17 lbf  
- **Pitch Up (Digital FLCS, Block 40/42+)** – 25 lbf  
- **Pitch Up (Analog FLCS, Block 30/32-)** – 40 lbf  

---

### Method 1: Using a Force Gauge (Recommended)
1. **Export Anchors** first to create a backup of any existing calibration.
2. Attach a calibrated force gauge to the stick just below the trigger.
3. Apply 50%, 75%, and 100% of the rated force in each direction.
4. Click **Set** next to the appropriate box corresponding to the axis you are working on.
5. Once verified, **Export Anchors** again to save your new calibration.
6. You may choose to **Lock Anchors** to prevent accidental changes.
   - Locked anchors can be unlocked later if needed using **Unlock Anchors**.
   - Locking provides protection but is reversible if you need to recalibrate.

#### ⌨️ Keyboard Shortcuts for Faster Calibration
When working with high forces (up to 40 lbf), using the mouse can be difficult. The Developer tab includes keyboard shortcuts to streamline the calibration process:

- **Period (.)** – Moves focus to the next **Set** button in sequence
  - Order: Roll Left (100%, 75%, 50%) → Roll Right (100%, 75%, 50%) → Pitch Down (100%, 75%, 50%) → Pitch Up Digital (100%, 75%, 50%) → Pitch Up Analog (100%, 75%, 50%)
  - The focused button will be highlighted in **bright green**
- **Enter** – Activates the currently focused **Set** button
  - Captures the current raw axis value and stores it in the corresponding anchor field

**Recommended Workflow:**
1. Press **Tab** or click the first **Set** button (Roll Left 100%) to give it focus
2. Apply the target force with the force gauge
3. Press **Enter** to capture the anchor value
4. Press **Period (.)** to move to the next anchor
5. Repeat steps 2-4 through all anchor points

This allows you to perform the entire calibration sequence without taking your hand off the stick or trying to precisely aim the mouse while pulling with significant force.

---

### Method 2: Estimation (No Gauge Available)
If you don't have a force gauge:
1. **Export Anchors** first to create a backup.
2. Deflect the stick to what you want to represent as the maximum (100%) force. Click **Set Anchor**.
3. Estimate halfway and three-quarter deflections for 50% and 75% values.
4. **Export Anchors** again to save your estimated calibration.

⚠️ Estimated anchors reduce accuracy. Use only if proper equipment is not available.

---

## 💾 Backup and Restore Workflow

**For ALL devices (especially those shipped after 8/15/2025 with factory anchors):**

### First-Time Setup
1. Open Developer Mode (**Shift + D**)
2. Click **Read Anchors** to load the factory calibration
3. **Immediately click Export Anchors** and save the file with a descriptive name (e.g., `InvictusStick_SN12345_FactoryAnchors.json`)
4. Store this file in multiple safe locations:
   - Cloud storage (Google Drive, Dropbox, etc.)
   - Local backup drive
   - Email it to yourself

⚠️ **This backup is irreplaceable.** Your device's anchors are unique and cannot be recreated without sending it back to Invictus for recalibration.

### Restoring Lost Anchors
If anchors are accidentally overwritten or corrupted:
1. Click **Import Anchors** and select your backup file
2. Review the loaded values in the Developer tab
3. Click **Write Anchors** to apply them to the device
4. Verify the anchors with **Read Anchors**
5. Lock anchors to prevent future accidents

---

## ✅ Best Practices
- **IMMEDIATELY export anchors** when you first receive your device and save the file in a safe location (cloud storage, multiple backups).
  - Force anchors are unique to your specific device and cannot be recreated without professional calibration equipment.
- **Do not modify anchors** on devices shipped after 8/15/2025 unless absolutely necessary.
- Always **Read Anchors** before writing.
- **Export Anchors** before making any changes to create a backup.
- Only **Lock Anchors** if:
  - You have confirmed accurate values with a force gauge, or
  - You are Invictus staff finalizing calibration.
- Lock anchors to protect against accidental changes; you can unlock them if recalibration is needed.
- When **Importing Anchors**, only use files that were exported from the same device.
- Treat anchors as **factory calibration** unique to your device — they cannot be transferred between devices.  

---

👉 If you believe your anchors are incorrect, contact [Invictus Cockpit Systems Support](https://invictuscockpits.com) before making any changes.
