# FAQ

**Why not just use Windows' Game Controllers (joy.cpl)?**
joy.cpl uses the old WinMM API, which only reports the first 32 buttons. AIM
Ghost Joysticks have 128, so joy.cpl can't show most of them. AIM Joystick Probe
reads the device a different way (DirectInput / RawInput) with no such cap.

**Does it work with non-AIM controllers?**
Yes — any joystick, throttle, or gamepad. The cockpit-control labels only apply
to AIM Ghost Joysticks; other devices simply show button numbers.

**My throttle/slider axis sits at −1.00. Is it broken?**
No. Axes that rest at one end (throttles, sliders) read −1.00 at rest. Move it and
the value changes.

**A button shows green even though I'm not pressing anything.**
That button may be stuck or wired closed. The **held** count in the BUTTONS header
is a quick way to spot it.

**The window won't stay in front of my sim.**
Turn on **Always on top** (top-right). It keeps the Probe above other windows so
you can read button numbers while binding.

**Is it free? Can I share it?**
It's free to use. Yes, you can share it.  You can even share it with your commercial customers, just so long as you don't modify, rebrand, or reverse engineer it. 
