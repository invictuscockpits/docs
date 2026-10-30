# Display Layout

> [!NOTE]
> Requires AIM Cockpit Manager **1.6.0** or later.

Multi-monitor cockpits depend on Windows keeping every display in the same position and resolution. Windows does not always cooperate: graphics driver updates, unplugging a display, or sometimes just a reboot can shuffle the arrangement, and suddenly your MFD exports render on the wrong glass and your sim viewports are scrambled.

The **Display Layout** section of [Settings](settings.md) fixes this with a snapshot:

- **SAVE CURRENT LAYOUT** records the position, resolution, refresh rate and turn (portrait or landscape) of every connected display, exactly as arranged right now. Do this once, when everything is where it belongs.
- **RESTORE SAVED LAYOUT** puts every display back to the saved arrangement in one atomic step.

The section says whether your monitors still match the saved layout, or that Windows has moved or turned them since.

Displays are recognized by the monitor itself, not by the number Windows gives it (DISPLAY1, DISPLAY5 and so on), which can change from one day to the next.

---

## Keep this layout

Turn on **Keep this layout** and the manager puts the saved layout back by itself whenever Windows changes your screens, for example after the PC sleeps or a monitor wakes up late. A screen that came back turned the wrong way is turned back too.

It waits until the screens have stopped changing, and never touches a screen while a full-screen game is on it. If Windows keeps changing the layout back, the manager stops after three tries and tells you, until the layout changes again.

> [!IMPORTANT]
> To change your screens on purpose, turn **Keep this layout** off first, then arrange them, **SAVE CURRENT LAYOUT**, and turn it back on. Otherwise the manager puts the old layout back.

---

## Automatic restore with Hot Start

Tick **Restore display layout first** in the Flight Session section and [Hot Start](hot-start.md) applies your saved layout before launching anything, so the sim always starts with displays where the cockpit expects them.

---

## Notes

- Save a new snapshot after any deliberate change to your monitor setup, or restore will faithfully return you to the old arrangement.
- Restore only affects displays that are currently connected. A display that's unplugged is left out rather than blocking the rest. With some saved displays missing, the ones that are connected get their turn and resolution back, but not their position.

**See also:** [Cockpit Displays in DCS](cockpit-displays-in-dcs.md), [Cockpit Displays in BMS](cockpit-displays-in-bms.md), [Hot Start](hot-start.md)
