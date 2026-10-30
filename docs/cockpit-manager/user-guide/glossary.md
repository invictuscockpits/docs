# Glossary

**AIM Displays**: The DCS monitor setup the manager installs, picked under **Monitors** in DCS Options → System. Called **AIM MFDs** before 2.6.0.

**AIM Network**: Avionics Interface Modular Network. The name for the Invictus Cockpit Systems cockpit networking platform. Covers the AIM boards, the manager software, and the protocol that connects them.

**AIM Ghost Joystick**: A virtual HID joystick device created by the AIM driver. Required for BMS input; not used by DCS or the boards themselves. The F-16C needs four; the driver supports up to five.

**Airframe**: The aircraft your cockpit is built for, chosen on the manager's **Home** page. It decides which panels the wizard offers, what Console Panels lists, and what the sim integration drives.

**Align**: Sizing and moving a display board's picture so it sits in your bezel's or data plate's window. **Align** on the display's card on [Instruments](instruments.md).

**Board**: A device the manager reads switches from and drives lamps on. Either an AIM board (Sidewinder or Phoenix, on the cockpit network over PoE Ethernet) or an Open Hardware board (your own Arduino, Teensy, Pico or ESP32, over USB).

**BMS**: Falcon BMS. A community-developed F-16 flight simulator.

**Callback**: BMS's name for a bindable cockpit function. The manager's keyfile maps cockpit controls to BMS callbacks.

**Console Panels**: The page under **Avionics** that shows the airframe one console at a time: a tab per console, a card per panel, and every control with its wiring and live state. Learn mode, calibration and the lamp test live here.

**DCS**: DCS World. A combat flight simulator made by Eagle Dynamics.

**DIY display**: A DED, PFLD or FFI display board you built yourself. It runs the same firmware as an Invictus display and needs your Open Hardware key to show anything.

**FFI**: Fuel flow indicator. The F-16's rolling-drum fuel flow counter. An ESP32 display board with a small SH1106 OLED can show it; see [Open Hardware](open-hardware.md).

**GPIO**: General Purpose Input/Output. A digital pin on the board that can read a switch (input) or drive an indicator lamp (output).

**HID**: Human Interface Device. The USB device class that covers keyboards, mice, and game controllers. BMS reads cockpit inputs via HID.

**I²C**: A two-wire serial bus (SDA + SCL) used to connect external components like a Caution Panel to AIM board expansion channels.

**Instruments**: The page under **Avionics** that lists every gauge and screen of the airframe, how each one is built, the display boards that show them, and the caution panel. See [Instruments](instruments.md).

**Invictus display**: A DED, PFLD or FFI display board from Invictus. It is signed at the factory, so it works as soon as it is plugged in and never asks for a key.

**JST PH**: The connector family used on all AIM board signal headers. 2mm pitch. All signal connections (switches, encoders, pots) use JST PH except backlighting channels.

**Keyfile**: A BMS `.key` file that maps cockpit controls to BMS callbacks. The manager generates `Invictus AIM F-16.key` during BMS setup.

**Lamp matrix**: A MAX7219 on an Open Hardware board used to light lamps instead of giving each lamp a pin of its own. Each chip lights up to 64 LEDs from three pins, and up to four chips can be chained.

**Learn mode**: **Learn wiring** on Console Panels. The manager watches the board's pins while you move each control and records which pin it is on, so you can wire first and assign afterwards.

**MAX7219**: An LED driver chip that runs 7-segment digits or up to 64 single LEDs from three pins (DIN, CLK, LOAD). The manager uses it for the UHF readouts, the caution panel on Open Hardware boards, and the lamp matrix.

**Mechanical**: A gauge built with a real needle on a motor, picked on [Instruments](instruments.md). The others are **Screen**, **LED** (the oxygen FLOW blinker only) and **None**.

**Micro MATE-N-LOK**: The TE Connectivity connector used on AIM board backlighting channels (TE 2-1445093-2 board header, 1445022-2 wire-side housing). 3mm pitch, 2-position.

**MonitorSetup.lua**: A DCS configuration file that defines which desktop pixel regions DCS uses for secondary display viewports. The manager generates `AIM_MFDs.lua` in your DCS Saved Games folder.

**Open Hardware**: Building panels on your own Arduino, Teensy, Raspberry Pi Pico or ESP32 boards. The manager installs its firmware on them over USB and sets them up like AIM boards. Also the page in the sidebar where those boards appear, where their firmware is installed, and where the key is entered (called DIY Devices before 2.6.0).

**Open Hardware key**: The license key that unlocks installing firmware on and setting up Open Hardware boards, and DIY displays. Bought at invictuscockpits.com and entered once in the manager, on the Open Hardware page. One key unlocks all your DIY devices. AIM boards and Invictus displays never need one.

**OTA**: Over-the-Air. The method used to flash firmware to AIM boards over the cockpit network, without USB.

**Phoenix**: The AIM panel board with 16 GPIO pins and 8 I²C channels. No potentiometer/ADC channels.

**PoE**: Power over Ethernet. AIM boards are powered by **IEEE 802.3at** (PoE+) switches.

**Pot / Potentiometer**: An analog rotary sensor with three terminals. Used for volume knobs, trim wheels, BARO knobs, and other continuously-variable controls. Sidewinder boards have 8 potentiometer channels (P1-P8); Phoenix has none.

**P1-P8**: The eight analog potentiometer channels on a Sidewinder board. Numbered separately from GPIO pins.

**Rotary encoder**: A knob with click stops that reports steps as it turns, on two pins, rather than a position. Any pot in the catalog can be wired as one; the manager counts the clicks and keeps the knob's value.

**Resistor ladder**: A chain of equal resistors that lets a rotary switch put a different voltage on one analog channel at each position, so the switch takes one input instead of one pin per position. See [Resistor Ladder Rotary Switches](resistor-ladder-rotary-switches.md).

**RTT Client**: A BMS application (`RTTClient64.exe`, in `[BMS install]\Tools\RTTRemote\`) that reads cockpit display textures exported by BMS and renders them into windows on secondary monitors on the **same PC**. This is what the manager configures via **Apply BMS Displays**.

**RTT Server**: A BMS feature that streams cockpit display textures **over a local network to a different computer** (so a second PC can show your MFDs/DED/etc.). The manager does not configure RTT Server and leaves its settings untouched.

**RTTRemote**: The BMS tool **folder** (`[BMS install]\Tools\RTTRemote\`) that contains both RTT Client and RTT Server, along with `RTTClient.ini`. It's a location, not a feature.

**Sidewinder**: The AIM panel board with 46 GPIO pins, 8 potentiometer channels (P1-P8), 2 I²C channels, and 2 SPI channels.

**SPI**: Serial Peripheral Interface. A four-wire bus (CLK, MOSI, MISO, CS) used to connect display and LED shift-register ICs to the board. Each SPI channel can carry multiple devices via separate CS lines.

**TM1637**: A 7-segment display module with its own driver, on a clock pin and a data pin. Open Hardware boards can use them for the UHF readouts.

**Unconfigured**: A panel no board has yet. On Console Panels and Instruments, **Configure** lists your boards, or adds a new one, and opens the board's setup with the panel ticked.

**VFT5**: Viper Force Transducer Gen 5. The Invictus USB side-stick controller. Connects directly over USB; does not use the AIM Network, but is configurable in Cockpit Manager.

**X27.168**: A small gauge stepper motor made for car instrument clusters, with its own end stop. The usual choice for a physical gauge needle.

---

**See also:** [What You Need](what-you-need.md), [FAQ](faq.md)
