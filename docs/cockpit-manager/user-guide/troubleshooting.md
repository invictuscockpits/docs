# Troubleshooting

Quick-reference for common problems. Each section links to the relevant wiki page for full context.

---

## Board won't appear on the Network page

> [!TIP]
> From manager **1.6.0**, start with [Network Health](network-health.md) (Network sidebar, **Network health** button). It checks every layer in order and the first red light tells you exactly which of the steps below to look at, so you don't have to walk them all.

- Confirm the PoE switch provides **802.3at** power. AIM boards require 802.3at. They are not compatible with 802.3af-only switches.
- Check the switch link light for the port the board is plugged into. No link light = cable or port issue.
- Confirm the PC's cockpit network adapter has the correct static IP (`10.24.6.1`). Use the manager's **Fix it for me** button on the Network page if the adapter isn't configured yet. See [Set Up the Cockpit Network](set-up-the-cockpit-network.md).
- If your PC has Hyper-V, WSL, VMware, or VirtualBox installed, a virtual network adapter may have taken over the cockpit's addresses; see the next section.
- Power-cycle the board. Hold until the link light returns, then wait 10-15 seconds for the board to boot and announce itself.

---

## Boards worked before, then vanished after a reboot

If Hyper-V, WSL, or a VM hypervisor is installed, its virtual switch (`vEthernet` / `VMnet` adapters in `ipconfig`) claims its own subnet, and Hyper-V's **Default Switch picks a new random subnet at every boot**. When it lands on `10.24.6.x`, two interfaces claim the cockpit subnet and Windows can route board traffic into the virtual switch instead of the cockpit NIC. Your configuration still looks correct, `10.24.6.1` bound, manager **Listening**, but boards don't appear.

**Check:** `ipconfig`. Any `vEthernet` or `VMnet` adapter holding a `10.24.6.x` address is the conflict. Fixes (subnet reservation, re-homing the switch, or disabling the adapter) are in the **Virtual adapters** section of [Set Up the Cockpit Network](set-up-the-cockpit-network.md). From manager v1.5.0, the Network page flags this automatically, and running **Fix** installs a permanent subnet reservation that prevents it entirely.

---

## Board appears but shows UNCONFIGURED

The board booted but hasn't been set up yet, or a previous save didn't complete. Click the board row to open the setup wizard. See [Add Your First Board](add-your-first-board.md).

---

## Board disappears after saving

The board reboots to apply its new configuration. Wait 15-20 seconds. It will reappear with a green dot. If it doesn't come back, check the PoE switch link light and try power-cycling.

---

## A switch doesn't respond when operated

Switch states are visible in the **Avionics → Panels** view. The manager reflects the state of your physical panels directly. It is not synced to the sim. When you operate a switch on the panel, the corresponding control in the Panels view should toggle. When you click a switch in the manager, it can trigger an action in the sim.

If a switch doesn't respond when physically operated:

- Confirm the control is assigned to a GPIO pin. Without a pin assignment the board doesn't know which input to listen to. See [Assign Controls to Pins](assign-controls-to-pins.md).
- Check your wiring: one switch leg to the GPIO pin, the other to GND. Polarity doesn't matter.
- The board must be saved and rebooted after any pin assignment change.
- Try a different GPIO pin. A damaged pin won't respond even with correct wiring.

---

## A rotary switch briefly snaps back to its previous position

When you turn a multi-position rotary, the display jumps to the new position, flicks back to the old one for a moment, then settles. This happens because the switch's contacts pass through a gap between positions, and a too-short settle window lets that in-between moment read as a real change.

The manager already guards rotaries with a 100 ms settle window by default. If a particular switch still does this (contact style varies between rotary brands), right-click that control in the panels view and choose **Adjust response time** (manager 1.6.0 and later), then raise the value until the snap-back stops. Saving sends the change to the board, which restarts for a moment.

---

## A potentiometer reads jitter or wrong values

- If the pot is not yet wired, right-click it in the live view and select **Mute**. Unwired pots float and show noise.
- Confirm the supply wire goes to **3.3V**, not 5V. Using 5V on a pot channel can damage the board.
- Run calibration: right-click the pot → **Calibrate**, sweep full range several times, then Save. See [Test and Calibrate](test-and-calibrate.md).
- Keep wiring runs under 1 meter. Long unshielded runs pick up noise.

---

## Controls appear in the manager but do nothing in DCS

- Confirm the DCS integration is installed (green "Installed" on the DCS Integration card on the home page). See [Set Up DCS](set-up-dcs.md).
- Confirm DCS is running and you are loaded into a mission with an F-16C. The integration is aircraft-specific.
- Hover the control in the manager. If the tooltip says the control is not modeled in DCS, DCS doesn't simulate that function.
- Confirm the correct sim is selected in the manager (DCS, not BMS).

---

## Controls work in DCS but wrong ones fire

Two controls are sharing the same pin. Open the pin assignment view. Conflicts are highlighted in red. Reassign one control to a free pin. See [Assign Controls to Pins](assign-controls-to-pins.md).

---

## DCS cockpit lights and displays don't update

- Confirm the DCS integration is installed and up to date.
- Ensure you are in the cockpit with engines running. Some indicators only change when aircraft systems are active.
- If a specific display (UHF, DED) is blank, check that the relevant DCS module exports are working. Some third-party module versions have broken export hooks.

---

## BMS receives no inputs

- Confirm the AIM Ghost Joystick driver is installed and shows the correct device count (**[N] of [N] devices ready**). See [Install the Virtual-Joystick Driver](install-the-virtual-joystick-driver.md).
- Confirm the keyfile is loaded in BMS and current: **BMS KEYFILE** card on the home page should show **Installed**, not **Update available**. See [Load the Keyfile](load-the-keyfile.md).
- Confirm BMS was launched with **"Launch without applying overrides"** ticked. Launching with overrides applied regenerates the keyfile and wipes your bindings.

---

## BMS keyfile shows "Update available"

Your catalog has changed since the last export (a manager update added new bindings, or you changed pin assignments). Open **Setup BMS keyfile** and click **Run export**. Then reload the keyfile in BMS. See [Set Up Falcon BMS](set-up-falcon-bms.md).

---

## Caution panel lamps lit in wrong positions

The TLC59281 daisy-chain bit order is reversed from what the catalog expects. Swap the physical order of the two TLC59281 ICs in the chain. See [Indicator and Caution Lights](indicator-and-caution-lights.md).

---

## UHF or CMDS display shows nothing

- Confirm firmware is v2.2.0 or newer. Check the Firmware page. See [Update Board Firmware](update-board-firmware.md).
- For UHF: the MAX7219 requires a 5V supply and 74AHCT125 level shifter on the SPI lines. 3.3V is not sufficient.
- Confirm the SPI channel in Step 2 of the board wizard matches the physical wiring.
- Confirm DCS integration is installed and you're in a cockpit. Displays update from DCS string exports.

---

## Board firmware OTA update fails

- Check the PoE switch link light during the transfer. A momentary dropout aborts the upload.
- If the board shows "firmware may be too old to update over the network," flash once over USB to get a current build onto the board. See [Update Board Firmware](update-board-firmware.md).

---

## Manager won't check for updates

- Confirm internet access is available. The manager reaches `api.github.com`.
- If you see "GitHub returned HTTP 403," the API rate limit was hit. Wait a few minutes and try again via **Settings → CHECK NOW**.

---

**See also:** [Get Support](get-support.md), [FAQ](faq.md), [Set Up the Cockpit Network](set-up-the-cockpit-network.md), [Add Your First Board](add-your-first-board.md)
