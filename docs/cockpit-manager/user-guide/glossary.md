# Glossary

**AIM Network**: Avionics Interface Modular Network. The name for the Invictus Cockpit Systems cockpit networking platform. Covers the AIM boards, the manager software, and the protocol that connects them.

**AIM Ghost Joystick**: A virtual HID joystick device created by the AIM driver. Required for BMS input; not used by DCS or the boards themselves. The F-16C needs four; the driver supports up to five.

**Airframe**: The aircraft your cockpit is built for, chosen on the manager's **Home** page. It decides which panels the wizard offers, what Console Panels lists, and what the sim integration drives.

**Board**: A device the manager reads switches from and drives lamps on. Either an AIM board (Sidewinder or Phoenix, on the cockpit network over PoE Ethernet) or an Open Hardware board (your own Arduino, Teensy, Pico or ESP32, over USB).

**BMS**: Falcon BMS. A community-developed F-16 flight simulator.

**Callback**: BMS's name for a bindable cockpit function. The manager's keyfile maps cockpit controls to BMS callbacks.

**Console Panels**: The page under **Avionics** that lists every panel and control of the airframe with its wiring and live state, and where learn mode, calibration and the lamp test live.

**DCS**: DCS World. A combat flight simulator made by Eagle Dynamics.

**DIY Devices**: The page where Open Hardware boards appear, where their firmware is installed, and where the Open Hardware key is entered.

**GPIO**: General Purpose Input/Output. A digital pin on the board that can read a switch (input) or drive an indicator lamp (output).

**HID**: Human Interface Device. The USB device class that covers keyboards, mice, and game controllers. BMS reads cockpit inputs via HID.

**I²C**: A two-wire serial bus (SDA + SCL) used to connect external components like a Caution Panel to AIM board expansion channels.

**JST PH**: The connector family used on all AIM board signal headers. 2mm pitch. All signal connections (switches, encoders, pots) use JST PH except backlighting channels.

**Keyfile**: A BMS `.key` file that maps cockpit controls to BMS callbacks. The manager generates `Invictus AIM F-16.key` during BMS setup.

**Learn mode**: **Learn wiring** on Console Panels. The manager watches the board's pins while you move each control and records which pin it is on, so you can wire first and assign afterwards.

**Micro MATE-N-LOK**: The TE Connectivity connector used on AIM board backlighting channels (TE 2-1445093-2 board header, 1445022-2 wire-side housing). 3mm pitch, 2-position.

**MonitorSetup.lua**: A DCS configuration file that defines which desktop pixel regions DCS uses for secondary display viewports. The manager generates `AIM_MFDs.lua` in your DCS Saved Games folder.

**Open Hardware**: Building panels on your own Arduino, Teensy, Raspberry Pi Pico or ESP32 boards. The manager installs its firmware on them over USB and sets them up like AIM boards.

**Open Hardware key**: The license key that unlocks installing firmware on and setting up Open Hardware boards. Bought at invictuscockpits.com, entered once on the DIY Devices page. AIM boards never need one.

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

**VFT5**: Viper Force Transducer Gen 5. The Invictus USB side-stick controller. Connects directly over USB; does not use the AIM Network, but is configurable in Cockpit Manager.

---

**See also:** [What You Need](what-you-need.md), [FAQ](faq.md)
