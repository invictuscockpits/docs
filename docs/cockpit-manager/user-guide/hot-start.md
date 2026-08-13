# Hot Start

> [!NOTE]
> Requires AIM Cockpit Manager **1.6.0** or later.

Hot Start launches your whole flight session with one click. It's the yellow and black striped button at the bottom of the sidebar, and it's also available from the manager's tray icon, so you can start a session without even opening the window.

When you click it, the manager starts the simulator selected on the Home page plus every companion app you've added (kneeboard, voice attack, launchers, whatever you fly with), in order, each waiting its own delay before the next one starts. It can also restore your saved monitor arrangement first so every cockpit display lands on the right screen. See [Display Layout](display-layout.md).

Clicking the small **i** circle on the button shows a summary and a shortcut to the setup section.

---

## Set up your sequence

Open **Settings** and find the **Flight Session** section.

- **ADD DCS** or **ADD BMS** adds your simulator with the install path detected automatically.
- **ADD APP…** adds anything else: point it at the program's `.exe`.
- Each app row has:
    - a **wait** time in seconds: how long Hot Start pauses after starting this app before launching the next one. Give sims a generous head start if later apps depend on them.
    - an **Admin** checkbox for apps that need to run elevated. Windows will show its administrator prompt for these.
    - arrows to reorder, a checkbox to temporarily disable an entry without deleting it, and **✕** to remove it.
- **Restore display layout first** makes Hot Start apply your saved monitor arrangement before starting anything. See [Display Layout](display-layout.md).

---

## DCS and BMS in the same list

Keep both sims in the list if you fly both. Hot Start is sim-aware: entries tagged to a simulator only launch when that simulator is selected on the Home page, so a list containing DCS and BMS never starts both at once. Apps you add yourself launch for either sim.

---

## Notes

- Progress appears as status messages while the sequence runs, and a summary when it finishes.
- If an app's path stops being valid (moved, uninstalled), Hot Start skips it and tells you rather than stopping the sequence.
- The tray icon's right-click menu has **Hot start (launch session)** for starting a session while the manager sits in the tray. See the **App Behavior** section in [Settings](settings.md) for tray and start-with-Windows options.
