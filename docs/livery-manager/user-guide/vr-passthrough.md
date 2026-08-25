# VR Passthrough Cockpit

!!! warning "Beta"
    The VR Passthrough cockpit is a beta release. It works end to end, and
    we're refining it with tester feedback; report anything odd through
    **Report an Issue** in the app sidebar.

![The VR Passthrough page](images/vr-passthrough.png)

The VR Passthrough page sets up a mixed reality cockpit: you fly DCS in a
headset while seeing your real, physical cockpit through passthrough. The
manager installs a special cockpit livery that paints every physical surface
of the virtual cockpit in a chroma-key color. Virtual Desktop then replaces
that color with the camera feed, so everything below the canopy rails becomes
your real pit while the HUD, canopy, outside world, and airframe stay in the
headset. The passthrough boundary follows the jet's own 3D geometry as you
move your head.

## What you need

- A physical cockpit to sit in. The livery is built for 1:1 replica pits;
  every switch, gauge, and panel you see is the real one in front of you.
- A Quest 3 (or similar headset) running **Virtual Desktop** with
  passthrough chroma keying.
- The DCS F-16C module. More aircraft profiles are on the way, and you can
  wire in your own (see Cockpit profiles below).

## Install the cockpit livery

Pick your aircraft in the profile selector, then click **Install cockpit
livery**. The manager downloads the latest livery, installs it into your
DCS Saved Games folder, and adds a small livery-scan helper mod that DCS
needs before it will load cockpit liveries from Saved Games. Nothing is
written into the game installation for this step.

The livery installs under its own name, so your stock cockpit is untouched.
Switch between the passthrough cockpit and the normal one any time in DCS
under **Options → Special → F-16C → Customized Cockpit**. After installing
or switching, always close DCS completely and restart it; DCS only scans
for liveries at startup.

**Remove** uninstalls both the livery and the helper mod cleanly.

!!! note "About that dropdown"
    The Viper's cockpit-livery dropdown has been broken in DCS itself for
    years: the cockpit reads the selection from a different place than the
    options screen writes it. The manager works around this automatically
    when it applies your settings, which is also why the dropdown starts
    working once the manager has set things up.

## Recommended DCS settings

The chroma key works best with specific renderer settings. Reflections
paint moving highlights over the key color, shadows darken it, and lens
effects bloom across it; any of these can punch holes in the passthrough.
The page audits every recommended setting and shows what differs.

Click **Apply all** with DCS fully closed. The manager patches the settings
file directly and keeps a backup alongside it; **Restore backup** puts your
old settings back. DCS must be closed because it rewrites its settings file
on exit and would overwrite the changes.

The applied settings are: canopy and MFD reflections off (both the F-16C
special options and the global graphics toggle), shadows flat/off, SSAO off,
SSLR off, cockpit global illumination off, lens effects off, and motion blur
off. Everything else, including your resolution and VR settings, is left
alone.

## Night mode

At night, DCS's lighting leaves the cockpit too dark for the chroma key to
work. The optional **night lighting patch** solves this: after applying it,
turn the instrument lighting knobs up at night and the cockpit keys
correctly after dark. Day flying is completely unchanged with the knobs off.

This is the one feature that modifies a file in the DCS installation (the
F-16C cockpit model), so applying it shows a Windows administrator prompt.
The manager keeps a pristine backup of the original file, and **Restore
original** puts it back at any time. Two things to know:

- **DCS updates and repairs quietly undo the patch.** Nothing breaks; the
  cockpit simply goes back to dark nights. Re-apply the patch from this page
  after updating.
- **Strict multiplayer servers** with pure-client integrity checks will flag
  the modified cockpit model. Use **Restore original** before flying on
  those servers, and re-apply afterward.

## Virtual Desktop setup

On the headset, use Virtual Desktop with the **VDXR** runtime and
**HEVC 10-bit** at the highest bitrate your setup sustains. In the
passthrough settings, enable chroma keying with:

| Setting | Value |
| --- | --- |
| Key color | red 255, green 0, blue 255 |
| Similarity | 15 to 20 percent |
| Smoothness | 5 to 10 percent |

For night flying, apply the night lighting patch and raise Similarity a few
points if dim corners of the pit stop keying.

## Cockpit profiles

The profile selector at the top of the page chooses which aircraft
everything on the page operates on. Profiles that ship with the manager
(the F-16C today) carry everything built in: the right folders, the right
settings, the loader workaround, and the night patch where one exists.

**Add profile...** wires in an aircraft the manager doesn't ship a profile
for yet. You'll need the cockpit unit folder name (the folder DCS uses
under `Liveries`, for example `Cockpit_F-18C`; the folder button lets you
pick it from your game installation instead of typing it) and the options
section name the aircraft uses in DCS's settings file. The loader section
and release tag are optional and only needed for special cases. Custom
profiles install liveries from local zip files, and **Remove** deletes
them again; built-in profiles can't be removed.

## Updates

Invictus cockpit liveries carry a version stamp. The page compares your
installed version against the latest release and shows both under the
install button; when a newer livery is available the button changes to
**Update to v...**. Livery updates are independent of app updates, so
improvements ship as soon as they're ready.

## Troubleshooting

- **The cockpit isn't magenta in DCS.** Restart DCS completely; liveries
  only load at startup. Then check all three status pills on the page are
  green and that **Options → Special → F-16C → Customized Cockpit** shows
  the passthrough livery.
- **Glare or reflections punch holes in the passthrough.** Run **Apply
  all** under Recommended DCS settings with DCS closed. If you changed
  graphics settings recently, re-run it; DCS sometimes reintroduces
  reflections.
- **The cockpit is green or dark at night.** Apply the night lighting
  patch, then turn the instrument lighting knobs up. If nights went dark
  again after a DCS update, re-apply the patch.
- **A multiplayer server rejects you.** Use **Restore original** in the
  night mode section, fly, then re-apply the patch afterward.
