# Test and Calibrate

**What you'll do:** verify that every wired control reads correctly in the manager, and calibrate your potentiometers and ladder-wired rotary switches so they map cleanly to the sim.

## Before you begin

- At least one panel has pins assigned. See [Assign Controls to Pins](assign-controls-to-pins.md).
- Your controls are physically wired to the board.

---

## Console Panels

**Avionics**, then **Console Panels**, lists every panel of your airframe by cockpit zone, with every control on it. No simulator needed.

![Console Panels with a panel expanded, showing the Wired to and Live columns](images/test-live-view.png)

Expand a zone, then a panel. Each control's row shows what it is, which board and pin it is **wired to**, and its **live** state. Flip a switch or turn a knob on the physical panel. The Live column should respond immediately. Work through each control one at a time.

The arrow buttons beside the live state drive the control from the manager, which is how you send a switch position to the sim without touching the panel. The **⋯** button at the right end of a row opens that control's menu: mute, invert, response time, calibration, and a lamp test.

### Reading the page

| What you see | What it means |
|---|---|
| Switch flips in sync with the physical switch | Correct wiring and pin assignment |
| Switch doesn't respond at all | Wrong pin, or a wiring issue; see below |
| Switch always shows as ON | GND and the pin are shorted, or the switch is normally closed. **Invert switch wiring** in the ⋯ menu fixes the second case |
| Pot moves when you turn the knob | Correct wiring and channel assignment |
| Pot doesn't move | Wrong analog channel or a wiring issue; see below |
| Pot moves but is noisy or jittery | Long wiring run picking up noise, or an unwired analog channel; see below |
| Rotary switch shows the wrong position | On a ladder-wired rotary, calibrate the positions; see below |
| A knob on a rotary encoder jumps 20 percent per click, or runs backwards | Calibrate the encoder; see below |

---

## Calibrate a potentiometer

Raw pot readings rarely span the full range the sim expects. Calibration tells the manager where the physical minimum and maximum are, so it can translate them accurately.

1. Click the pot's **⋯** button and choose **Calibrate range…**.
2. Slowly turn the knob from one mechanical stop to the other several times. The manager watches the incoming values and captures the range on its own. No buttons to click while sweeping.
3. When the bar spans the full range, click **Save**.

![Pot calibration dialog with the Reverse direction toggle, showing Raw min / Raw max / Current / Span as the knob is swept](images/test-calibrate-pot.png)

If the result doesn't look right, the bar starts mid-range or stops short, click **Clear saved** and sweep the knob again from scratch.

> [!TIP]
> If the pot reads backwards (turning clockwise decreases the value instead of increasing it), tick **Reverse direction** in the calibration dialog. It flips the pot's travel instantly, no rewiring and no reboot, and any range you've already calibrated is flipped to match. (If you'd rather fix it in hardware, swapping the pot's 3.3 V and GND wires does the same thing.)

## Calibrate a ladder-wired rotary switch

A rotary switch wired through a resistor ladder reports a voltage, and the manager needs to know which voltage means which position. Click its **⋯** button, choose **Calibrate positions…**, and park the switch on each position in turn. The full steps are on [Resistor Ladder Rotary Switches](resistor-ladder-rotary-switches.md).

## Calibrate an encoder-wired knob

A pot wired as a rotary encoder counts clicks. Encoders differ in how many steps they report per click, and knobs differ in how many clicks should span the travel, so the manager learns both from you.

1. Click the knob's **⋯** button and choose **Calibrate encoder…**.
2. Turn the knob exactly five clicks in one direction. The dialog counts the steps and shows how many that is per click. If the count stays at zero, the knob is at the end of its travel: turn it the other way.
3. Set **Clicks from one end of the travel to the other**. Twenty is a good default for a volume or brightness knob.
4. Tick **Reverse direction** if the value runs the wrong way.
5. Click **Save**. The setup is sent to the board again with the new count range.

## Test a lamp

Lamps normally follow the sim. To check a freshly wired one, click the lamp's **⋯** button and choose **Test lamp**. Every cell of that indicator lights for three seconds.

---

## Diagnosing problems

### Menu fixes for switches

Two entries in the **⋯** menu solve the most common switch complaints without touching a soldering iron:

**Invert switch wiring**: if a toggle reads backwards (up shows as down), it was wired to the opposite throw. This flips it in software, instantly, and the fix persists with the board's configuration. No rework, no reboot.

**Adjust response time…**: how long the board waits for a switch's contacts to settle before reporting a new position. Raise it if a rotary switch briefly snaps back to its previous position when you turn it; lower it if a control feels slow. Saving sends the change to the board; an AIM board restarts for a moment. Rotaries default to 100 ms.

### A switch doesn't respond

1. **Check the pin assignment.** Open the board, click **Edit**, then **3. Pins**, and confirm the control is on the pin you wired.
2. **Check the wiring.** With the board powered, use a multimeter in continuity mode across the switch terminals to confirm it's switching. Then confirm the wire from the pin goes all the way back to the board header. No broken joints.
3. **Try a neighboring pin.** Temporarily assign the control to an adjacent pin and bridge that pin to GND with a wire. If the manager responds, the original pin is fine and the issue is in the wiring to that pin. If it still doesn't respond, the pin may be damaged. Try a different one.

### A pot doesn't move

1. **Check the channel.** Confirm the pot is assigned to an analog channel (P1 to P8 on a Sidewinder, an analog pin on an Open Hardware board), not a GPIO pin.
2. **Check the supply wires.** The wiper wire carries the signal, but the pot needs the board's supply and GND on the outer terminals to produce one. Confirm both are wired.

### A pot is jittery or noisy

- **Unassigned analog channels** float and read random values if nothing is connected to them. If you see jitter on a control you don't plan to wire, click its ⋯ button and choose **Mute this control**. If you do plan to wire it later, you can ignore the jitter for now. It goes away once a pot is connected and calibrated.
- **Long wiring runs** can pick up interference. Try a shorter run or twisted-pair wiring between the pot and the board.
- **Dirty pot wiper.** On older pots, a worn wiper causes noise. Try exercising the knob through its full range a few times; if it doesn't improve, the pot may need replacing.

---

**Next:** [Swap or Replace a Board](swap-or-replace-a-board.md) or continue to [Set Up DCS](set-up-dcs.md)
