# FAQ

---

**Do I need AIM boards to use DCS with my cockpit panels?**

Yes. AIM boards are how your physical switches, knobs, and pots connect to the manager. The manager receives input from the boards over the cockpit network and translates it to DCS commands.

---

**Do I need AIM boards for BMS?**

Yes. In addition to the boards, BMS also requires the AIM Ghost Joystick virtual driver, which the manager installs. See [Install the Virtual-Joystick Driver](install-the-virtual-joystick-driver.md).

---

**Does the manager work with other simulators?**

Not currently. DCS World and Falcon BMS are the supported sims. MSFS, X-Plane, and others are planned for future releases.

---

**How many boards can I connect?**

There's no hard limit imposed by the software. Practical limits come from your PoE switch port count and the 10.24.6.0/24 subnet (up to 253 devices). Most F-16C builds use 4-8 Sidewinder and Phoenix boards.

---

**Can I mix Sidewinder and Phoenix boards?**

Yes. Each board is configured independently. Panels are assigned to whichever board they're physically wired to. The mix is entirely up to you.

---

**Does the Phoenix board support potentiometers?**

No. The Phoenix has 16 GPIO pins and 8 I²C channels, but no potentiometer/ADC channels. Use a Sidewinder board for any panel that needs analog inputs. See [What You Need](what-you-need.md).

---

**Can I use 5V for potentiometers?**

No. use the board's **3.3V** supply pin for pots. Feeding 5V into a potentiometer channel will damage the board.

---

**Do I need pull-up resistors for switches?**

No. The board's GPIO pins have internal pull-ups enabled, and the headers have series resistors on the GPIO lines. Wire switches directly. No external components needed.

---

**Can I use Hall-effect sensors instead of potentiometers?**

Yes. Hall sensors wire the same way as pots (3.3V supply, signal to P1-P8, GND return) and are calibrated the same way. See [Test and Calibrate](test-and-calibrate.md).

---

**What PoE switch do I need?**

Any **IEEE 802.3at** (PoE+) managed or unmanaged switch works. AIM boards require 802.3at. They are not compatible with 802.3af-only switches. See [What You Need](what-you-need.md).

---

**The manager says the DCS integration is "Installed" but cockpit lights don't work. Why?**

The DCS integration handles communication between DCS and the manager. It needs to be installed for anything to work. But cockpit lights and displays also need physical output hardware (indicator LEDs, caution panel, displays) wired to your boards, firmware v2.2.0+, and the correct panel assignments in the board wizard. See [Indicator and Caution Lights](indicator-and-caution-lights.md) and **UHF and CMDS Displays**.

---

**How many AIM Ghost Joystick devices does the manager create?**

Up to five. Four is typical for a full F-16C build. They are named **AIM Ghost Joystick 1**, **AIM Ghost Joystick 2**, and so on. The manager creates exactly the number the catalog requires; the **Create [N] devices** button in the BMS keyfile dialog shows the correct count. See [Install the Virtual-Joystick Driver](install-the-virtual-joystick-driver.md).

---

**I launched BMS and my cockpit controls stopped working. What happened?**

BMS was launched with overrides applied, which regenerated the keyfile and overwrote your bindings. Always tick **"Launch without applying overrides"** in the launcher. Re-export the keyfile from the manager and reload it in BMS to restore bindings. See [Load the Keyfile](load-the-keyfile.md).

---

**Can I use this with the Viper Force Transducer (VFT5) stick?**

Yes. the VFT5 connects separately over USB and has its own setup in the manager's Firmware page. It doesn't require an AIM board. The manager handles both the stick and the panel boards independently.

---

**Can I export a reference of all my cockpit pin assignments?**

Yes. Step 4 of the board wizard has an **Export pinout** button that saves a printable reference. You can also re-run Step 4 at any time on a configured board. Keep these exports somewhere safe. They're invaluable when you need to trace a wire months after the cockpit was built. See [Assign Controls to Pins](assign-controls-to-pins.md).

---

**See also:** [Troubleshooting](troubleshooting.md), [Glossary](glossary.md), [Get Support](get-support.md)
