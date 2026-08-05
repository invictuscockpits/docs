<img src="https://github.com/user-attachments/assets/6075a8ff-14d9-410f-a82d-dd931e4c34b9" width="1200">

# Axes Settings

The **Axes Settings** tab allows you to calibrate, tune, and customize each axis on your Invictus HOTAS device.  
This page explains every option and what it does.

---

## Axis List
- Up to **8 axes** are supported: X, Y, Z, Rx, Ry, Rz, Slider 1, Slider 2.
- Each axis has its own settings panel. Only the axes supported by your board and grip are displayed. If for some reason too many are showing, you can check the hide buttons at the bottom of the window to hide individual axes.

---

## 🎛️ FLCS Mode and Force Scaling

At the top of the Axes Settings tab, you'll find two important options for devices with force-sensing axes (strain gauges):

### **FLCS Mode**
Selects the F-16 flight control system variant your device should emulate:
- **Analog FLCS** (Block 30/32-) – Earlier F-16 variants with 40 lbf maximum pitch-up force
- **Digital FLCS** (Block 40/42+) – Newer F-16 variants with 25 lbf maximum pitch-up force

This setting automatically adjusts the pitch-up axis calibration to match the selected FLCS mode.

### **Proportional Force Scaling**
Allows you to reduce the maximum force required across all axes:
- **Full FLCS Force** (100%) – Authentic F-16 force levels
  - Roll: 17 lbf
  - Pitch Down: 17 lbf
  - Pitch Up: 25 lbf (Digital) or 40 lbf (Analog)
- **75% FLCS** – 75% of full force
- **50% FLCS** – 50% of full force (most comfortable for extended sim sessions)

> ⚠️ **Note:** These features require **factory force anchors** (devices shipped after 8/15/2025) or manually calibrated anchors set in Developer Mode. Without anchors, these controls will not function correctly.

---

## Calibration Settings

### **Min / Center / Max**
- **Calib Min** – the lowest raw value the axis should recognize (full left/down travel).  
- **Calib Center** – the neutral rest position.  
- **Calib Max** – the highest raw value the axis should recognize (full right/up travel).  

Typical force levels:
- **Roll (X)**: Min = full roll left (~17 lbf), Max = full roll right (~17 lbf)  
- **Pitch (Y)**: Down = 17 lbf, Up = 25 lbf (digital FLCS) or 40 lbf (analog FLCS)  

⚠️ **Tip:** Use **Start Calibrate → push/pull in both directions with the amount of fore you want to represent full deflection → Stop & Save** to auto-fill these values.  
For more precision, you can enter values manually by noting the **Raw Value** (gray bar) at each force level.

---

### **Center Checkbox**
- When checked: lets you define a fixed center point (recommended).  
- Best practice: set **Center = 0** for consistent results.  
- **Default:** Roll (X) and Pitch (Y) ship with Center **checked** and value **0**. All other axes (Z, Rx, Ry, Rz, Slider 1, Slider 2) default to unchecked for throttle/slider use cases.

This is especially important on the pitch axis, since up and down forces differ.

---

## Output Settings

### **Output Enabled**
- Toggles whether the axis sends data to the PC.  
- Useful if your device has extra axes you don’t want exposed to Windows.

### **Inverted**
- Reverses the output direction.  
- Example: pulling back = positive pitch instead of negative.  
- Normally not needed, since devices ship with axes oriented correctly.

---

## Filter and Hysteresis Compensation

### **Filter**
- Smooths noisy input.  
- Levels: **Off, 1–7** (higher = smoother but slower).  

Note: Strain gauges are very sensitive. Filtering can reduce jitter, but at the expense of responsiveness. Use sparingly — for force-sensing grips, **Hysteresis Compensation** is usually the better tool.

### **Hysteresis Compensation**
Force-sensing grips exhibit mechanical hysteresis: the flexure doesn't return to exactly the same ADC value after every release, so axis output can drift slightly off zero at rest. A large static deadband hides this but robs you of the fine-control value of a force sensor.

- When enabled, the firmware captures the actual rest position after each release and treats it as a **dynamic zero**.  
- Result: clean zero output at rest, with fine proportional response as soon as you apply a light push in either direction from rest (~250 raw ADC counts of activation).  
- Activation is **symmetric** around rest, so pushing against the hysteresis direction feels identical to pushing with it.  
- Recommended for all force-sensing Invictus grips; available as a per-axis checkbox on each axis's Extended Settings panel (beneath the Offset spinbox).

> 💡 Start with Hysteresis Compensation enabled on Roll (X) and Pitch (Y). If you still see drift at rest, increase the axis **Filter** level slightly.

---

## Function Settings

### **Function**
- Optional virtual button outputs triggered by axis movement.  
- Options:
  - **None** – no button functions  
  - **Plus** – button press when axis moves positive  
  - **Minus** – button press when axis moves negative  
  - **Equal** – button press when axis is centered  

### **Step Divider**
- This reduces the resolution of the axis by dividing the raw sensor counts into larger “steps.”
Example: if the divider is set to 2, the axis reports every 2nd count; if set to 4, it reports every 4th. This effectively coarsens the resolution, which can make the axis less sensitive but smoother in some use cases.
- Default = **50** (recommended). 

### **Prescaler**
- This speeds or slows the sampling/update rate of the axis. Instead of processing every raw reading from the ADC, the firmware skips a number of samples according to the prescaler value. The result is fewer updates per second to the host, which reduces noise and load but also lowers responsiveness. 
- Default = **100** (recommended).  


👉 **In layman’s terms**: 

- **Step-Divider**: How fine the “ruler” is for your axis.

- **Prescaler**:How often you check that ruler.


### **Resolution**
- Determines bit-depth of axis reporting.  
- Gen 1–3 boards: **12-bit**  
- Gen 4 boards: **16-bit**  
- Automatically set by board selection. Do not change unless troubleshooting abnormal values.

### **Offset Angle**
- Shifts axis zero point in **15° increments**.  
- Reserved for future use (e.g., simulating the F-16 SSC stick angle). Normally leave at 0.

---

## Source Selection

### **Main Source**
- Selects the hardware input for this axis:
  - None  
  - Encoder  
  - Analog pin (A0–A15, B0–B15, C13–C15)  
  - I²C sensor (Gen 4 boards only)  

> ⚠️ Automatically set by board and grip selection. Do not change.

### **Secondary Source**
- Optional redundancy input.  
- Not used in current devices.

### **I²C Address**
- Only used for I²C sensors on Gen 4 boards.  
- Automatically populated. Do not change.

---

## Axes → Buttons (Axis-Generated Buttons)
- Converts axis movement into virtual button presses.  
- Options for **Button 1, 2, 3**:
  - **Down**, **Up**, **Reset**, **Center**, or **Function Enable**  
- Useful for throttle detents (idle, afterburner) or trim wheels.  

> Example: Set Button 1 = “Idle Detent,” Button 2 = “Afterburner” on a throttle axis.

---



👉 Next: see [Troubleshooting](troubleshooting.md) for common axis calibration issues and fixes.
