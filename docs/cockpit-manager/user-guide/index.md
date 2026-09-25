# AIM Cockpit Manager: User Guide

Welcome. This guide covers everything you need to get your cockpit wired up, configured, and flying.

![AIM Cockpit Manager's Home page, where you pick the airframe and the simulator](images/home-overview.png)

## What the AIM platform is

The **AIM network** is the backbone of an Invictus cockpit. Each AIM panel board (Sidewinder, Phoenix) connects to your PC over a single Ethernet cable that carries both data and power. No separate power supplies, no USB hubs, no driver installs for the boards. The **AIM Cockpit Manager** is the Windows app that ties it all together: it finds your boards, walks you through setup, and keeps your switches, knobs, and displays in sync with the sim while you fly.

From version 2.0 the manager also drives panels you build on your own **Arduino, Teensy, Raspberry Pi Pico or ESP32** boards. Those plug in over USB and need an Open Hardware key. See [Open Hardware](open-hardware.md).

## What the manager does

- Finds every AIM board on your cockpit network, and every Open Hardware board on USB, and guides you through a setup wizard.
- Lets you assign each switch, knob, and pot to a pin, or learn the wiring by flipping the switches, then test it live. No round-trips to the simulator.
- Installs the sim integration for DCS World and Falcon BMS.
- Puts your MFDs, DED, RWR, HUD, and EHSI on extra monitors in both sims.
- Updates itself and your AIM board firmware over the air. Open Hardware boards update over their USB cable.

## Where to start

Pick your airframe and simulator on the **Home** page first. Everything else follows from that choice.

**Setting up for the first time?** Work through these in order:

1. [What You Need](what-you-need.md). Hardware and software checklist before you begin
2. [Install the Manager](install-the-manager.md). Download, install, first launch
3. [Set Up the Cockpit Network](set-up-the-cockpit-network.md). Get your PC talking to AIM boards (skip this for USB boards)
4. [Add Your First Board](add-your-first-board.md). The setup wizard
5. [Assign Controls to Pins](assign-controls-to-pins.md). Map your switches and knobs

**Already running, looking for something specific?**

| I want to… | Go to |
|---|---|
| Set up DCS World | [Set Up DCS](set-up-dcs.md) |
| Set up Falcon BMS | [Set Up Falcon BMS](set-up-falcon-bms.md) |
| Put displays on extra monitors | [Cockpit Displays in DCS](cockpit-displays-in-dcs.md) or [Cockpit Displays in BMS](cockpit-displays-in-bms.md) |
| Set up my VFT5 stick | [VFT5 Side-Stick](vft5-side-stick.md) |
| Use my own Arduino, Teensy, Pico or ESP32 | [Open Hardware](open-hardware.md) |
| Wire a rotary switch to one input instead of one pin per position | [Resistor Ladder Rotary Switches](resistor-ladder-rotary-switches.md) |
| Wire indicator lights or the caution panel | [Indicator and Caution Lights](indicator-and-caution-lights.md) |
| See what every panel and control does | [Airframes](../airframes/index.md) |
| Fix something that's not working | [Troubleshooting](troubleshooting.md) |
| Update the manager or board firmware | [Update the Manager](update-the-manager.md) |

## A note on sims

DCS World is the primary and most complete integration. Falcon BMS is fully supported for the F-16C. When a control isn't simulated in a particular sim, the wizard's Pins step shows it: each control carries a **DCS** tag and a **BMS** tag only for the sims that model it.
