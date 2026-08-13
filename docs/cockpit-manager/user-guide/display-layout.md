# Display Layout

> [!NOTE]
> Requires AIM Cockpit Manager **1.6.0** or later.

Multi-monitor cockpits depend on Windows keeping every display in the same position and resolution. Windows does not always cooperate: graphics driver updates, unplugging a display, or sometimes just a reboot can shuffle the arrangement, and suddenly your MFD exports render on the wrong glass and your sim viewports are scrambled.

The **Display Layout** section of [Settings](settings.md) fixes this with a snapshot:

- **SAVE CURRENT LAYOUT** records the position, resolution, and refresh rate of every connected display, exactly as arranged right now. Do this once, when everything is where it belongs.
- **RESTORE SAVED LAYOUT** puts every display back to the saved arrangement in one atomic step.

---

## Automatic restore with Hot Start

Tick **Restore display layout first** in the Flight Session section and [Hot Start](hot-start.md) applies your saved layout before launching anything, so the sim always starts with displays where the cockpit expects them.

---

## Notes

- Save a new snapshot after any deliberate change to your monitor setup, or restore will faithfully return you to the old arrangement.
- Restore only affects displays that are currently connected. A display that's unplugged is left out rather than blocking the rest.

**See also:** [Cockpit Displays in DCS](cockpit-displays-in-dcs.md), [Cockpit Displays in BMS](cockpit-displays-in-bms.md), [Hot Start](hot-start.md)
