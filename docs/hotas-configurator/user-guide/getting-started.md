# Getting Started

This page explains the **left-side dropdowns and buttons** in the Invictus HOTAS Configurator.  
These define which hardware you’re configuring, how it maps to your simulator, and how settings are read/written.

---

## 🖥️ Board Selection (Gen 1–3, Gen 4)
- Selects which Invictus control board you are using.  
- **Gen 1–3**: Legacy Invictus SSC / VFT boards. All work the same way.  
- **Gen 4**: Current generation with improved ADC resolution, pin mapping, and quality-of-life features.  
- Choosing the correct board ensures pins, ADC resolution, and internal limits are set correctly.

---

## ✋ Grip Selection
- Select which grip (joystick handle) is attached to your base.  
- Supported grips include:
  - **Invictus Viper**
  - **Thrustmaster® Warthog**
  - **Thrustmaster® Cougar**
  - **Tianhang Grip (26-button)**
  - **Tianhang Grip (30-button)**

> ⚠️ **Note:** Tianhang offers two grips (26-button and 30-button).  
> These grips do **not** map the same way.  
> Be sure to select the correct Tianhang Grip profile in the dropdown to ensure buttons are labeled and function correctly.

- Grip selection automatically loads:
  - The correct **logical button map** (so button names match your hardware)  
  - The correct **shift register setup** (button count and type)

---

## 🎮 Simulator Selection
- Choose which simulator you are configuring for:
  - **DCS World**
  - **Falcon BMS**
  - **MSFS** (and others as added)

Why it matters:
- **Falcon BMS** only supports one POV hat. The Configurator automatically remaps POV2–POV4 to normal buttons in this case.  
- **DCS World** and **MSFS** retain full POV functionality.  

This allows one grip profile to adapt automatically to multiple sims.

---

## 📥 Read Settings from Device
- Reads the **current settings** from your Invictus device.  
- Populates the Configurator with the values stored on your device.  
- Always use this before making changes.

⚠️ If you skip this step, you may overwrite calibration and factory values with defaults.

---

## 📤 Write Device Settings
- Sends the settings from the GUI to the device.
- Applies all changes immediately.
- Use only after verifying board, grip, sim, and calibration selections.

---

## 💾 Safe Workflow
1. Plug in your device
2. **Read Settings from Device**
3. Select **Board, Grip, and Sim**
4. Make adjustments if needed
5. **Write Device Settings**

---

## 📖 Getting Help

The **Visit Wiki** button (green text, below the Board dropdown) provides quick access to this documentation directly from the Configurator.

---

👉 Next: see [Overview](overview.md) for a walkthrough of each settings tab (Pins, Buttons, Axes, Advanced, Developer).
