# What You Need

Before you install the manager or plug anything in, make sure you have everything on this list. Missing any one item is the most common reason a first-time setup stalls.

There are two ways to connect panels: **AIM boards** over the cockpit network, and your own **Open Hardware boards** over USB. The network gear below is only for AIM boards.

## Computer

- **Windows 10 (21H2 or newer) or Windows 11**: 64-bit. The manager does not run on macOS or Linux.
- **For AIM boards, two network adapters**: one for your internet connection (Wi-Fi is fine), and one **wired Ethernet adapter** dedicated to the cockpit boards. Most desktop PCs already have a built-in Ethernet port; a USB-to-Ethernet adapter works if you don't have a spare port.
- **For Open Hardware boards, a free USB port per board**, and a USB cable that carries data. Many charger cables carry power only.

> [!IMPORTANT]
> The cockpit network runs on its own subnet, and the cleanest setup keeps it on its own Ethernet adapter, separate from your internet connection. A USB Ethernet adapter (about $15) is an easy way to add a dedicated cockpit port. If your PC has only one Ethernet port and you need internet on it too, it can be made to work: see **Internet and the cockpit on one Ethernet port** in [Set Up the Cockpit Network](set-up-the-cockpit-network.md).

## Network gear (AIM boards)

- **An IEEE 802.3at PoE switch**: sometimes labeled "PoE+" or "802.3at." Your boards draw power from the Ethernet cable. AIM boards require 802.3at. They are not compatible with 802.3af-only switches. An unmanaged switch is fine; you do not need managed VLANs or QoS.
- **Standard Cat5e or Cat6 patch cables**: one per board, run from the board to the PoE switch. Length limit is 100 m (328 ft) per Ethernet spec.

> [!TIP]
> If you're building a full pit, a small 8-port 802.3at PoE switch mounted inside the cockpit keeps the wiring clean. You only need one Ethernet cable running from the pit to the PC.

## Flight simulators

Install whichever you plan to use before running through the sim setup steps.

- **DCS World 2.9 or newer**: the manager installs the integration automatically; you don't need to edit any files by hand.
- **Falcon BMS 4.37 or newer**: fully supported as of manager v1.1.0. BMS 4.38+ is recommended for cockpit displays (RTTClient is more reliable on the newer build).

## Boards

You'll need at least one board to get anything working.

**AIM boards** are the Invictus panel boards. A **Sidewinder** has 46 GPIO pins, 8 potentiometer channels, 2 I²C channels and 2 SPI channels. A **Phoenix** has 16 GPIO pins and 8 I²C channels. See the product pages at invictuscockpits.com for details on what's in each board. AIM boards never need a key.

**Open Hardware boards** are your own Arduino, Teensy, Raspberry Pi Pico or ESP32 boards. From version 2.0 the manager installs its firmware on them over USB and sets them up with the same wizard. They need an Open Hardware key. See [Open Hardware](open-hardware.md) for the list of boards that work.

The **VFT5 force-transducer side-stick** connects via USB separately from the boards and has its own section: [VFT5 Side-Stick](vft5-side-stick.md).

## What you do *not* need

- A driver install for the boards. AIM boards are discovered over the network with no additional software, and Open Hardware boards use the serial drivers Windows already has.
- Admin rights for day-to-day use. The manager runs as a normal user. You'll need to approve one elevated action when setting up the cockpit network for the first time (the manager walks you through it).
- A DHCP server. AIM boards and the PC use static IPs on the cockpit subnet.

> [!NOTE]
> **Falcon BMS users:** BMS requires a virtual joystick driver to receive button and axis inputs from your cockpit hardware. The manager installs this for you. It's a one-time step covered in [Install the Virtual-Joystick Driver](install-the-virtual-joystick-driver.md). DCS World does not require it.

---

**Next:** [Install the Manager](install-the-manager.md)
