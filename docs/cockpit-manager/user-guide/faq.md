# FAQ

---

**Do I need AIM boards to use DCS with my cockpit panels?**

No. AIM boards are the simplest way: they connect over the cockpit network with no drivers and no key. From version 2.0 you can also use your own Arduino, Teensy, Raspberry Pi Pico or ESP32 boards over USB with an Open Hardware key. Either way the manager receives the inputs and translates them to DCS commands. See [Open Hardware](open-hardware.md).

---

**Do I need AIM boards for BMS?**

No, the same boards work for BMS. BMS also requires the AIM Ghost Joystick virtual driver, which the manager installs. See [Install the Virtual-Joystick Driver](install-the-virtual-joystick-driver.md).

---

**Do I need a key for AIM boards?**

No. The Open Hardware key only unlocks setting up your own boards. AIM boards are always free to set up.

---

**Does the manager work with other simulators?**

Not currently. DCS World and Falcon BMS are the supported sims. MSFS, X-Plane, and others are planned for future releases.

---

**How many boards can I connect?**

There's no hard limit imposed by the software. Practical limits come from your PoE switch port count and the 10.24.6.0/24 subnet (up to 253 devices) for AIM boards, and from free USB ports for Open Hardware boards. Most F-16C builds use 4-8 Sidewinder and Phoenix boards.

---

**Can I mix Sidewinder and Phoenix boards?**

Yes, and Open Hardware boards alongside them. Each board is configured independently. Panels are assigned to whichever board they're physically wired to. The mix is entirely up to you.

---

**Does the Phoenix board support potentiometers?**

No. The Phoenix has 16 GPIO pins and 8 I²C channels, but no potentiometer/ADC channels. Use a Sidewinder, or an Open Hardware board with analog inputs, for any panel that needs analog inputs. That includes a rotary switch wired through a resistor ladder. See [What You Need](what-you-need.md).

---

**Can a rotary switch use fewer pins?**

Yes. Wire it through a resistor ladder to one analog channel instead of one pin per position, on an AIM Sidewinder or an Open Hardware board. See [Resistor Ladder Rotary Switches](resistor-ladder-rotary-switches.md).

---

**Can I use a rotary encoder instead of a potentiometer?**

Yes, for any pot. In the wizard's Pins step change the pot's wiring to **Rotary encoder, two pins**, wire the encoder's common to GND and A and B to the two pins, then run **Calibrate encoder…** from Console Panels so the manager knows how many clicks span the travel. The sim still sees a pot. See [Test and Calibrate](test-and-calibrate.md).

---

**Can I use 5V for potentiometers?**

Not on an AIM board. Use the board's **3.3V** supply pin for pots. Feeding 5V into a potentiometer channel will damage the board. On an Open Hardware board, use that board's own supply: 3.3 V on a Pico or ESP32, and 5 V is fine on a 5 V Arduino.

---

**Do I need pull-up resistors for switches?**

No. AIM boards' GPIO pins have internal pull-ups enabled, and the headers have series resistors on the GPIO lines. Open Hardware boards use their built-in pull-ups. Wire switches directly between the pin and GND. No external components needed.

---

**Can I use Hall-effect sensors instead of potentiometers?**

Yes. Hall sensors wire the same way as pots (supply, signal to the analog channel, GND return) and are calibrated the same way. See [Test and Calibrate](test-and-calibrate.md).

---

**What PoE switch do I need?**

Any **IEEE 802.3at** (PoE+) managed or unmanaged switch works. AIM boards require 802.3at. They are not compatible with 802.3af-only switches. See [What You Need](what-you-need.md).

---

**The manager says the DCS integration is "Installed" but cockpit lights don't work. Why?**

The DCS integration handles communication between DCS and the manager. It needs to be installed for anything to work. But cockpit lights and displays also need physical output hardware (indicator LEDs, caution panel, displays) wired to your boards, firmware v2.2.0+ on AIM boards, and the correct panel assignments in the board wizard. See [Indicator and Caution Lights](indicator-and-caution-lights.md).

---

**How many AIM Ghost Joystick devices does the manager create?**

As many as the airframe needs: four for the F-16C. The driver supports up to five. They are named **AIM Ghost Joystick 1**, **AIM Ghost Joystick 2**, and so on; the **Create [N] devices** button in the BMS keyfile dialog shows the count. See [Install the Virtual-Joystick Driver](install-the-virtual-joystick-driver.md).

---

**I launched BMS and my cockpit controls stopped working. What happened?**

BMS was launched with overrides applied, which regenerated the keyfile and overwrote your bindings. Always tick **"Launch without applying overrides"** in the launcher. Re-export the keyfile from the manager and reload it in BMS to restore bindings. See [Load the Keyfile](load-the-keyfile.md).

---

**Can I use this with the Viper Force Transducer (VFT5) stick?**

Yes. The VFT5 connects separately over USB and has its own pages under **Flight Controls** and **Firmware**. It doesn't require a panel board. The manager handles the stick and the boards independently.

---

**Can I export a reference of all my cockpit pin assignments?**

Yes. The wizard's **Review** step, and an AIM board's page on the Network page, have an **Export pinout** button that saves a printable reference. Keep these exports somewhere safe. They're invaluable when you need to trace a wire months after the cockpit was built. See [Assign Controls to Pins](assign-controls-to-pins.md).

---

**See also:** [Troubleshooting](troubleshooting.md), [Glossary](glossary.md), [Get Support](get-support.md)
