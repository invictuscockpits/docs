# AIM Joystick Probe

A modern joystick tester for Windows that shows a controller's **complete**
button map — all **128** buttons of an AIM Ghost Joystick — not the 32 that
Windows' built-in **joy.cpl** stops at.

![AIM Joystick Probe](images/main-window.png)

## Why it exists

Windows' Game Controllers panel (`joy.cpl`) reads sticks through the legacy
**WinMM** API, which caps button reporting at **32**. AIM Ghost Joysticks expose
128 buttons, so joy.cpl literally can't show most of them. AIM Joystick Probe
reads the device through DirectInput / RawInput instead, so every button, axis,
and POV hat shows up.

It works with any controller — it just solves the AIM Ghost Joystick case
especially well.

## What you can do

- See live **buttons, axes, and POV hats** for any connected controller
- View the full **128-button** map, with each AIM Ghost button labelled with its
  **F-16C cockpit control**
- **Test all** — walk every button and confirm none are dead
- Read the **last button pressed** (handy when binding in DCS or BMS)
- Keep the window **always on top** of a running sim

## Pages

- [Getting Started](getting-started.md)
- [Reading Your Controller](reading-your-controller.md)
- [Test-All Mode](test-all-mode.md)
- [AIM Ghost Joysticks](aim-ghost-joysticks.md)
- [Updates](updates.md)
- [FAQ](faq.md)
