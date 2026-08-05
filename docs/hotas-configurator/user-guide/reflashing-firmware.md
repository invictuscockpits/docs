# Reflashing Firmware

Two paths are available for updating firmware on your Invictus device:

1. **Firmware Flasher (Recommended)** — update directly from the Configurator over USB.
2. **ST-Link Recovery** — emergency recovery for devices that can no longer be reached over USB (corrupt bootloader, bricked device).

---

# Firmware Flasher (Recommended)

For any working device, update firmware directly from the Configurator. No external tools required.

## Steps

Open the **Settings** tab in the Configurator. The Firmware Flasher section includes an on-screen guide that walks through the four steps:

1. **Press Read Device Settings** so that the current settings are loaded into the Configurator.
2. **Press Enter Flasher Mode.** The device reboots into its bootloader; the button turns green and reads *Ready to flash*.
3. **Press Flash Firmware** and select the new `.bin` file. Current releases ship with versioned filenames like `InvictusHOTASv2.4.2.8.bin`. A progress bar tracks flash progress.
4. **After flashing completes**, a *Firmware Updated* popup confirms success. Close it, then **Press Write Device Settings** to finalize your configuration on the new firmware.

> 💡 Step 4 is required. New firmware ships with its default config loaded on first boot, so your board type, sim software, and grip need to be re-written after every flash. The popup reminds you of this.

## Where to get firmware

Download the latest `.bin` from the [firmware releases page](https://github.com/invictuscockpits/invictus-ssc-firmware/releases/latest).

---

# ST-Link Recovery (Emergency Only)

If your device becomes unresponsive or cannot be updated via USB, you can recover it using an **ST-Link** programmer and **STM32 Cube Programmer** software.

---

## 🔗 Required Tools
1. **ST-Link Programmer**  
   [ST-Link Programmer](https://www.amazon.com/dp/B07SQV6VLZ?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_1)  
   - Any ST-Link V2 is suitable.  

2. **Pogo-Pin Clamp** *(optional)*  
   [Pogo-Pin Clamp](https://www.amazon.com/dp/B0DBT62LJT?ref_=ppx_hzod_title_dt_b_fed_asin_title_0_1)  
   - Needed only if your board does not have a 4-pin header.  
   - Must be 2.54 mm pitch.  

3. **STM32 Cube Programmer Software**  
   [STM32 Cube Programmer](https://www.st.com/en/development-tools/stm32cubeprog.html)  

---

<img src="https://raw.githubusercontent.com/invictuscockpits/HOTASConfigurator/main/src/Images/VFT_Controller_render.PNG" alt="Gen 3 Board" width="300" align="right">

## 🔌 Connecting the ST-Link
1. Locate the 4-pin header (or 4 through-hole pads) at the top of your control board.  
   From left to right:  
   - **3.3V** *(Do **not** connect to the 5V pin on the ST-Link)*  
   - **SWDIO**  
   - **SWCLK**  
   - **GND**  
2. Connect the ST-Link to the board using DuPont cables or a pogo-pin clamp:  
   - **3.3V → 3.3V**  
   - **SWDIO → SWDIO**  
   - **SWCLK → SWCLK**  
   - **GND → GND**  
3. Plug the ST-Link into your PC via USB.  

<br clear="left"/>

---

## 🖥️ Using STM32 Cube Programmer
1. Open **STM32 Cube Programmer**.  
2. Select **ST-LINK** as the connection type.  
3. Press **Connect**.  
   - If successful, device details will be displayed.  

---

## 🧹 Full Chip Erase
1. In Cube Programmer, go to the **Erasing & Programming** tab.  
2. Select **Full chip erase**.  
3. Run the erase.  
   - This removes all existing firmware from the chip.  

---

## 📂 Flashing the Bootloader
1. In the same tab, click **Browse** and select:  invictusbootloader.hex (Available in the [latest firmware release](https://github.com/invictuscockpits/invictus-ssc-firmware/releases/latest))  
2. Ensure **Verify programming** is checked.  
3. Press **Start Programming**.  
- The bootloader is written to the device.  

---

## ⚠️ Important: Do Not Flash the Application Yet
- It is recommended to flash **only the bootloader** using ST-Link.  
- With the bootloader installed, the device can be updated normally via the Invictus HOTAS Configurator.  

Steps:
1. Disconnect the ST-Link.
2. Connect the device to your PC via USB.
3. The device will automatically enter **Flasher Mode**.
4. Open the Invictus HOTAS Configurator, go to the **Settings** tab, and use the **Firmware Flasher** section.
5. Choose the `.bin` firmware file from the [latest firmware release](https://github.com/invictuscockpits/invictus-ssc-firmware/releases/latest).  

This process ensures:
- The bootloader is working correctly.  
- The Configurator can communicate with the device.  
- Application firmware loads through the normal update process.  

---

## ✅ Summary
- Use ST-Link + Cube Programmer only for **recovery** and flashing the **bootloader**.  
- Always flash the **application firmware** (`.bin` files) through the Invictus HOTAS Configurator.  
- This confirms proper USB communication and ensures your device works as intended.

