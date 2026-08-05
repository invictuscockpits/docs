# Axes Curves

> ⚠️ **Archived — Axes Curves tab is hidden in v2.4.2.4 and later.**  
> The tab has been removed from the Configurator UI pending a marker-alignment fix. Devices with saved curves in flash retain them, and the feature may return in a future release. This page is preserved for reference.

The **Axes Curves** tab lets you reshape how raw input values are translated into output values seen by Windows and simulators.  
This is useful for fine-tuning control feel, especially near the stick center or throttle detents.

---

## Overview
- Each axis uses an **11-point curve**.  
- Points are evenly spaced across the input range (0–100%).  
- Curves are stored per-axis in device settings.

---

## Editing Curves

### How to Adjust
1. Select the axis you want to edit.
2. Drag points with the mouse or enter values manually.
3. Click **Write Device Settings** to save.

### Default Curve
- Linear: input matches output (straight diagonal line).  

### Example Curves
- **Exponential** – shallow near center, steeper at edges (finer aim control).  
- **S-curve** – shallow at ends, steeper mid-travel (throttles, pedals).  
- **Inverted** – flips output if axis is inverted.  

---

## Options Per Axis
- **Enable/Disable Curve** – toggle shaping on or off.  
- **Reset Curve** – restore linear default.  
- **Output Preview** – shows live position with curve applied.

---

## Interaction with Axes Settings
- **Calibration (Min/Center/Max)** is applied first.  
- **Filters and Deadband** are applied before the curve.  
- The curve shapes the normalized value after calibration and filtering.

⚠️ Always calibrate axes first in **Axes Settings**, then adjust curves.

---

## Use Cases
- **Flight Stick (Pitch/Roll)**: Add exponential for smoother control around center.  
- **Throttle**: Add S-curve for fine control near idle and max, with quick response mid-range.  
- **Rudder Pedals**: Mostly linear, maybe small deadband at center.  


---

## Tips
- Make small changes; large jumps cause abrupt outputs.  
- Use Output Preview to confirm smooth travel.  
- Save multiple `.cfg` files with different curves (e.g., “Precision” vs “Arcade”) for quick switching.

---

👉 Next: see [Axes Settings](axes-settings.md) for calibration, filters, and deadband before applying curves.
