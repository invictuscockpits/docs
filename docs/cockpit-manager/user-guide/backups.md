# Backups

> [!NOTE]
> Requires AIM Cockpit Manager **1.6.0** or later.

The **Backups** section of [Settings](settings.md) protects the two things most painful to lose: your DCS control bindings and your BMS keyfile. It also backs up and restores the manager's own configuration, which makes moving to a new PC a two-click job.

All backups are timestamped zip files saved to **Documents\AIM Cockpit Manager Backups**. The section shows your recent backups with a **RESTORE** button next to each.

---

## Sim bindings

- **BACK UP DCS BINDINGS** archives your DCS input folder: every axis assignment, button binding, and modifier for every module.
- **BACK UP BMS KEYFILE** archives your Falcon BMS keyfile.

Restoring puts the archived files back exactly as they were. As a safety net, the manager makes one more backup of the current state right before any restore, so even a restore is reversible.

> [!TIP]
> The manager also makes an automatic safety backup of your keyfile every time you export to BMS, before the export touches anything. If an export ever goes wrong, the previous keyfile is in the backup folder.

---

## Whole-configuration export

- **EXPORT CONFIG…** writes a single file containing the manager's configuration: boards and pin assignments, calibrations, display assignments, settings, and launch sequence.
- **IMPORT…** loads one on another machine (or after a reinstall).

Export a config file whenever your cockpit reaches a state you'd hate to rebuild. Your boards themselves keep their own configuration onboard, so this is about the manager-side state: names, layouts, calibrations, and preferences.

---

**See also:** [Settings](settings.md), [Set Up DCS](set-up-dcs.md), [Load the Keyfile](load-the-keyfile.md)
