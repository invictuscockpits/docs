# FAQ

**Why not just use Windows' Game Controllers (joy.cpl)?**
joy.cpl uses the old WinMM API, which only reports the first 32 buttons. AIM
Ghost Joysticks have 128, so joy.cpl can't show most of them. AIM Joystick Probe
reads the device a different way (DirectInput / RawInput) with no such cap.

**Does it work with non-AIM controllers?**
Yes. It reads any joystick, throttle, or gamepad. The cockpit-control labels only apply
to AIM Ghost Joysticks; other devices simply show button numbers.

**My throttle/slider axis sits at −1.00. Is it broken?**
No. Axes that rest at one end (throttles, sliders) read −1.00 at rest. Move it and
the value changes.

**A button shows green even though I'm not pressing anything.**
That button may be stuck or wired closed. The **held** count in the BUTTONS header
is a quick way to spot it.

**The window won't stay in front of my sim.**
Turn on **Always on top** in [Settings](settings-snapshots-and-diagnostics.md#settings)
(the gear at the top right). It keeps the Probe above other windows so you can
read button numbers while binding.

**Two of my button boxes have the same name. How do I tell them apart?**
The Probe numbers devices that share a name, for example **Button Box (1)** and
**Button Box (2)**. Press a button on one and watch which row lights up in the
sidebar (see [Which device is that?](reading-your-controller.md#which-device-is-that)).

**The resolution column just says "sweep".**
The Probe hasn't seen enough of that axis yet. Move it slowly through part of
its range, or let it rest for a moment. See [Resolution](axes-and-sensors.md#resolution).

**The Hz pill shows 0.**
Most devices only send updates when something changes. Move an axis or press a
button. See [Report rate](reading-your-controller.md#report-rate).

**My device is plugged in but doesn't appear in the sidebar.**
Click **Copy diagnostics** and look at "Windows game controllers the Probe does
not see". If your device is listed there, please
[report it](https://github.com/invictuscockpits/aim-joystick-probe-releases/issues)
and paste the report. If it isn't listed, Windows doesn't see it as a game
controller either; check its cable, USB port and driver.

**The axis names changed after an update.**
The Probe now shows the names the device itself reports, the same as Windows'
Game Controllers panel. On an AIM Ghost Joystick, the seventh and eighth axes
are the Dial and the Slider; older versions called them Slider 1 and Slider 2.

**Is it free? Can I share it?**
It's free to use. Yes, you can share it.  You can even share it with your commercial customers, just so long as you don't modify, rebrand, or reverse engineer it. 
