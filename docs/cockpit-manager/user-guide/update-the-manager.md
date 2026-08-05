# Update the Manager

**What you'll do:** install a new version of AIM Cockpit Manager when one is available.

## How updates work

The manager checks for updates against the GitHub releases page for `invictuscockpits/aim-cockpit-manager-releases`. When a newer version is found, a banner appears at the top of the app window. The manager downloads the installer in the background; you run it when ready.

**Auto-check on launch** is on by default. You can turn it off in **Settings → Check for updates on launch** if you prefer to check manually.

---

## When an update is available

A banner appears at the top of the manager window:

> **AIM Cockpit Manager X.Y.Z is available. You are running A.B.C.**

Click **Download**. The banner updates to show download progress:

> **Downloading update X.Y.Z (45%)**

When the download completes:

> **AIM Cockpit Manager X.Y.Z is ready to install.**

Click **Run installer**. The installer launches with a standard Windows UAC prompt. Follow the prompts. The installer closes the manager automatically before replacing files.

The **View release notes** button opens the GitHub release page in your browser at any point during the process.

---

## Check for updates manually

Go to **Settings** and click **CHECK NOW** under the Software section. If an update is found, it switches to **GET UPDATE** and the banner appears at the top of the window.

---

## If something's wrong

| Problem | Fix |
|---|---|
| No banner appears even though you expect an update | Go to Settings and click CHECK NOW. If it still doesn't find one, confirm the release is published on the releases page. |
| "GitHub returned HTTP 403" error | The GitHub API rate limit was hit. Wait a few minutes and try again. |
| Network error | Check your internet connection. The manager needs access to `api.github.com`. |
| Installer fails to launch | The download may be incomplete. Try clicking Download again to re-fetch. |

---

**See also:** [Update Board Firmware](update-board-firmware.md)
