# Indicator and Caution Lights

**What you'll do:** configure physical cockpit indicator lamps and the caution panel so they light up from DCS and BMS sim state.

There are two distinct output types covered here:

- **Indicator lights**: individual lamps (gear lights, FLCS PWR, master caution, etc.) each driven by one GPIO pin on the board's I²C GPIO expander.
- **Caution panel**: the full 32-lamp caution/advisory panel driven by a TLC59281 shift-register chain over SPI.

> [!NOTE]
> Physical indicator and caution output requires **firmware v2.2.0 or newer**. Check your board's firmware version on the Firmware page before wiring.

---

## Indicator lights

### How they work

Each individual lamp connects to one GPIO pin on the board. The manager drives the pin high or low based on the sim state for that light. Gear down-and-locked, master caution, FLCS fault, etc. The board's GPIO expander handles the output; no external driver chip is needed for standard indicator lamps.

### Setting them up

Indicator lamps are part of the panel they belong to. You don't add them separately. When you select a panel in **Step 2** of the board wizard (for example, the gear panel or the eyebrow lights panel), the wizard automatically includes every lamp that panel contains.

In **Step 3: Pin Assignments**, each lamp appears as its own row. Assign each one to an available GPIO pin, the same way you assign switches. Each lamp needs its own pin.

> [!TIP]
> Use GPIO pins on the opposite side of the MCP23017 expander from your switch inputs if possible. Keeping outputs grouped separately from inputs makes troubleshooting easier later.

### Wiring

Connect the lamp's anode (positive leg) to the GPIO pin header, and cathode (negative leg) to GND. The GPIO pin drives high (3.3V) when the lamp should be on.

If you're using higher-current lamps, add a current-limiting resistor in series. Most standard indicator LEDs run well at 3.3V with a 100-330 Ω resistor. Check the LED's datasheet for its forward voltage and rated current.

---

## Caution panel

### How it works

The caution panel's 32 lamps are driven by a **TLC59281** constant-current LED shift register over SPI. All 32 lamps share one SPI channel. You assign the channel once and the firmware handles the rest. There is no pin-by-pin assignment for caution lamps.

The manager maps each DCS caution light argument (or BMS caution flag) to its corresponding TLC59281 output channel automatically, based on the panel catalog's hardcoded layout. You don't need to configure individual channels.

### Setting it up

**Step 2: Panels:** Check **Caution Panel** in the panel list. A slot dropdown appears. Select which SPI channel on your board the TLC59281 chain is wired to (**SPI Channel 1** or **SPI Channel 2**).

That's it. No Step 3 assignments are needed for caution lamp outputs. The 32-channel mapping is handled by the catalog.

### Wiring

Connect the TLC59281 chain's SPI input (SDI, CLK, LE, /OE) to the SPI channel header on your Sidewinder board. The TLC59281 is a daisy-chainable shift register. If you have two ICs for a full 32-lamp panel, chain the SDO of the first to the SDI of the second.

Power the TLC59281 at 3.3V or 5V depending on your lamp supply. The ESP32's SPI lines are 3.3V and are compatible with 3.3V-powered TLC59281 directly. If you run it at 5V, add a level shifter on the SPI lines.

The **/BLANK** (output enable) pin should be pulled low to enable outputs. If you leave it floating or pull it high, all lamps stay off regardless of the data sent.

> [!NOTE]
> If the caution lamps light in the wrong positions, the daisy-chain bit order may be reversed from what the catalog expects. Swap the first and last TLC59281 in the chain, or swap the two ICs' positions, to reverse the order.

---

## Check it worked

In the manager, go to the **Panels** page and select a panel with indicators. Load into a mission in DCS. Trigger the relevant cockpit state (put the gear down, activate master caution, etc.). The corresponding lamp on your panel should light.

For the caution panel, trigger a caution condition in DCS (engine fault, fuel low, etc.) and verify the correct lamp lights.

## If something's wrong

| Problem | Fix |
|---|---|
| Indicator lamp never lights | Check the GPIO pin assignment in Step 3. Confirm the pin is not also assigned to a switch input. Verify the lamp is wired anode → GPIO, cathode → GND. |
| Indicator lamp is always on | The GPIO may be floating high. Check the pin assignment and confirm the firmware version is 2.2.0+. |
| Caution panel lamps light in wrong positions | The TLC59281 daisy-chain bit order is reversed. Swap the order of the ICs in the chain. |
| Caution panel does nothing | Check that the SPI channel in Step 2 matches the physical wiring. Confirm /BLANK is pulled low. |
| Firmware page shows version older than 2.2.0 | Update board firmware before testing outputs. See [Update Board Firmware](update-board-firmware.md). |

---

**See also:** **UHF and CMDS Displays**, [Assign Controls to Pins](assign-controls-to-pins.md), [Update Board Firmware](update-board-firmware.md)
