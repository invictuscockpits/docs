# Backups

> [!NOTE]
> Requires AIM Cockpit Manager **1.6.0** or later.

The **Backups** section of [Settings](settings.md) protects the two things most painful to lose: your DCS control bindings and your BMS keyfile. It also backs up and restores the manager's own configuration, which makes moving to a new PC a two-click job.

All backups are timestamped zip files saved to **Documents\AIM Cockpit Manager Backups**. The section shows your recent backups, newest first, with a **RESTORE** button next to each. **SHOW ALL** lists every one.

---

## Sim bindings

- **BACK UP DCS BINDINGS** archives your DCS input folder: every axis assignment, button binding, and modifier for every module.
- **BACK UP BMS KEYFILE** archives your Falcon BMS keyfile.

Restoring puts the archived files back exactly as they were. As a safety net, the manager makes one more backup of the current state right before any restore, so even a restore is reversible.

> [!TIP]
> The manager also makes an automatic safety backup of your keyfile every time you export to BMS, before the export touches anything. If an export ever goes wrong, the previous keyfile is in the backup folder.

---

## Whole-configuration export

- **EXPORT CONFIG…** writes a single file containing the manager's configuration: boards and pin assignments, calibrations, muted controls, the gauge setup, the cockpit display setup, the saved monitor layout, settings, and the Hot Start sequence. It doesn't include your Open Hardware key; enter the key again on the other PC.
- **IMPORT…** loads one on another machine (or after a reinstall). It shows what the file will replace and asks first. Your current configuration is backed up, then the manager restarts to load the import.
- Every import leaves a **Manager settings** backup of what you had before. Click **RESTORE** next to it to go back; that also asks first and restarts the manager.

Export a config file whenever your cockpit reaches a state you'd hate to rebuild. AIM boards keep their own configuration onboard, and the manager holds the setup for Open Hardware boards and sends it whenever they connect, so an export carries everything the manager knows: boards and pins, names, layouts, calibrations, and preferences.

---

## If a saved file is damaged

The manager keeps the previous copy of each of its settings files. If one is damaged, say by a crash or a power cut in the middle of a save, the manager loads the last good copy and tells you so. The damaged file stays next to it with `.damaged` in its name, in case support needs it.

---

**See also:** [Settings](settings.md), [Set Up DCS](set-up-dcs.md), [Load the Keyfile](load-the-keyfile.md)
