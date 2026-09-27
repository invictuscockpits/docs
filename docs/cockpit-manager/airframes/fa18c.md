# F/A-18C

Every panel the manager knows on the F/A-18C, in the order the Console Panels page lists them: what the panel is, then each switch, knob, lamp and gauge on it, what its positions do, and what it takes to wire. The Docs button on a panel in the manager opens that panel's section on this page.

> [!NOTE]
> This airframe was generated from the simulator's own cockpit data. Panels marked **draft** have not been checked against a real cockpit yet, so names and grouping can still change. Wiring you record against a draft panel is kept when it is renamed.

Controls: 361. Panels: 57.

## Left Console

### FIRE TEST

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The fire and bleed air leak test switch, forward on the left console.

**FIRE TEST** · 3-position toggle, spring return · 2 pins

Tests the fire warning and bleed air leak detection loops. Spring-loaded back to the center.
**TEST A:** Checks loop A: the three fire lights, both bleed lights and the voice warnings come on.
**NORM:** Normal position.
**TEST B:** Checks loop B the same way.

### GROUND POWER

*Draft: generated from the simulator, not yet checked against a real cockpit.*

External power switch and the four ground power switches that feed aircraft systems while parked on a power cart.

**EXT PWR** · 3-position toggle · 2 pins

Connects external power once the ground crew has plugged it in.
**RESET:** Spring-loaded. Hold briefly to reset the external power monitor.
**NORM:** External power is used when it is available.
**OFF:** External power disconnected.

**GND PWR 1** · 3-position toggle, spring return · 2 pins

Selects which part of power group 1 runs from external power. Hold in A ON or B ON for three seconds and it stays there while external power is connected.
**A ON:** Group A powered.
**AUTO:** Normal, no ground power override.
**B ON:** Group B powered.

**GND PWR 2** · 3-position toggle, spring return · 2 pins

Same as GND PWR 1, for power group 2.

**GND PWR 3** · 3-position toggle, spring return · 2 pins

Same as GND PWR 1, for power group 3.

**GND PWR 4** · 3-position toggle, spring return · 2 pins

Same as GND PWR 1, for power group 4.

### GEN TIE

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The guarded generator tie switch on the outboard edge of the left console.

**GEN TIE** · 2-position toggle · 1 pin

Guarded. Resets the generator tie after a fault so one generator can power both buses again. The GEN TIE caution lights while it is in RESET.
**NORM:** Normal, guard closed.
**RESET:** Resets the generator tie.

### EXTERIOR LIGHTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Position, formation and strobe light controls. None of them work unless the exterior lights master switch on the left throttle is ON.

**POSITION** · Potentiometer · 1 analog input

Brightness of the red, green and white position lights, from OFF to BRT.

**FORMATION** · Potentiometer · 1 analog input

Brightness of the formation light strips, from OFF to BRT.

**STROBE** · 3-position toggle · 2 pins

Red anti-collision strobes on the tails.
**BRT:** Full brightness.
**OFF:** Strobes off.
**DIM:** Reduced brightness.

### FUEL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Fuel control panel: internal wing tank transfer, refueling probe, fuel dump and external tank transfer.

**INTR WING** · 2-position toggle · 1 pin

Controls fuel transfer from the internal wing tanks.
**NORM:** Wing tanks transfer normally.
**INHIBIT:** Wing tanks are held full.

**PROBE** · 3-position toggle · 2 pins

Moves the air refueling probe.
**EXTEND:** Probe out for tanking.
**RETRACT:** Probe stowed.
**EMERG EXTD:** Extends the probe using emergency power when normal extension fails.

**DUMP** · 2-position toggle · 1 pin

Dumps internal fuel overboard down to the reserve level.
**ON:** Dumping.
**OFF:** Not dumping.
DCS flips this switch on each press, so the manager presses it only when the sim and the panel disagree.

**EXT TANK CTR** · 3-position toggle · 2 pins

Transfer from the centerline drop tank.
**STOP:** No transfer.
**NORM:** Transfers when the internal tanks call for it.
**ORIDE:** Transfers even with weight on wheels.

**EXT TANK WING** · 3-position toggle · 2 pins

Transfer from the wing drop tanks.
**STOP:** No transfer.
**NORM:** Transfers when the internal tanks call for it.
**ORIDE:** Transfers even with weight on wheels.

### APU AND ENGINE CRANK

*Draft: generated from the simulator, not yet checked against a real cockpit.*

APU start switch, the engine crank switch used to start each engine from APU air, and the APU READY light.

**APU** · 2-position toggle · 1 pin

Starts the APU. The switch is held electrically in ON and drops back to OFF about a minute after the second generator comes on line.
**ON:** Starts the APU.
**OFF:** Shuts the APU down.

**APU READY** · Lamp · output

Green light: the APU is running and ready to crank an engine.

**ENG CRANK** · 3-position toggle, spring return · 2 pins

Sends APU air to one engine's starter. Held electrically, it returns to OFF by itself once that engine's generator is on line.
**LEFT:** Cranks the left engine.
**OFF:** No engine cranking.
**RIGHT:** Cranks the right engine. Starting the right engine first gives brake pressure.

### FCS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Flight control system panel: rudder trim, takeoff trim, FCS reset and the guarded GAIN switch.

**RUD TRIM** · Potentiometer · 1 analog input

Rudder trim knob. It biases the flight control computers; the pedals do not move.

**T/O TRIM** · Push button · 1 pin

Button in the center of the rudder trim knob. On the ground, hold it to set roll and yaw trim to neutral and the stabilators to 12 degrees nose up for takeoff. TRIM shows on the DDI until it is let go.

**FCS RESET** · Push button · 1 pin

Resets flight control system faults that have cleared.

**GAIN** · 2-position toggle · 1 pin

Guarded. Switches the flight controls to fixed gains when air data is bad.
**NORM:** Normal gains, guard closed.
**ORIDE:** Fixed gains for a failed air data system.

### COMMUNICATION

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Communication control panel: audio volumes, radio relay and transmit selection, IFF master and Mode 4, crypto, and the ILS channel.

**VOX** · Potentiometer · 1 analog input

Volume for voice-operated intercom.

**ICS** · Potentiometer · 1 analog input

Intercom volume.

**RWR** · Potentiometer · 1 analog input

Radar warning receiver tone volume.

**WPN** · Potentiometer · 1 analog input

Weapon tone volume, such as the Sidewinder seeker growl.

**MIDS B** · Potentiometer · 1 analog input

Volume for MIDS voice channel B.

**MIDS A** · Potentiometer · 1 analog input

Volume for MIDS voice channel A.

**TCN** · Potentiometer · 1 analog input

TACAN identifier tone volume.

**AUX** · Potentiometer · 1 analog input

Auxiliary audio volume.

**COMM RLY** · 3-position toggle · 2 pins

Relays one radio through the other.
**CIPHER:** Relay in secure mode.
**OFF:** No relay.
**PLAIN:** Relay in plain mode.

**G XMT** · 3-position toggle · 2 pins

Transmits on the guard frequency with the selected radio.
**COMM 1:** Guard on radio 1.
**OFF:** Normal.
**COMM 2:** Guard on radio 2.

**IFF MASTER** · 2-position toggle · 1 pin

**NORM:** Normal replies.
**EMER:** Replies to every interrogation with the emergency code.

**MODE 4** · 3-position toggle · 2 pins

How Mode 4 interrogations are reported to you.
**DIS/AUD:** Valid interrogations show M4 OK; unknown ones also give an IFF voice alert.
**DIS:** Valid interrogations show M4 OK; unknown ones give no warning.
**OFF:** No indication either way.

**CRYPTO** · 3-position toggle, spring return · 2 pins

Handles the stored Mode 4 keys. Spring-loaded to NORM from ZERO.
**HOLD:** Keeps the keys through shutdown. Works only with the gear down.
**NORM:** Keys are erased when the jet is shut down.
**ZERO:** Erases the keys immediately. Mode 4 stops working.

**ILS** · 2-position toggle · 1 pin

Where the ILS channel comes from.
**UFC:** Set the channel on the UFC.
**MAN:** Use the channel knob on this panel.

**ILS CHANNEL** · Rotary selector · 20 pins, or 1 analog input

Manual ILS channel, 1 to 20. Used when the ILS switch is in MAN.

### ANTENNA SELECT

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Antenna selection for radio 1 and the IFF transponder.

**COMM 1 ANT** · 3-position toggle · 2 pins

**UPPER:** Upper antenna.
**AUTO:** Picks the better antenna.
**LOWER:** Lower antenna.

**IFF ANT** · 3-position toggle · 2 pins

**UPPER:** Upper antenna.
**BOTH:** Both antennas, the normal setting.
**LOWER:** Lower antenna.

### OXYGEN

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Onboard oxygen generating system (OBOGS) controls.

**OBOGS** · 2-position toggle · 1 pin

**ON:** Oxygen system running.
**OFF:** Oxygen system off.

**OXY FLOW** · Potentiometer · 1 analog input

Oxygen flow valve, from OFF to maximum.

### MC AND HYD ISOL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Mission computer power and the hydraulic isolate override, aft on the left console.

**MC** · 3-position toggle, spring return · 2 pins

Turns off one mission computer. Spring-loaded from both ends.
**1 OFF:** Mission computer 1 off.
**NORM:** Both on.
**2 OFF:** Mission computer 2 off.

**HYD ISOL** · 2-position toggle · 1 pin

**NORM:** Normal hydraulic isolation.
**ORIDE:** Overrides the isolation valves for a ground test.

### LEFT WALL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The left cockpit wall: the essential circuit breakers, the countermeasures dispense button and the nuclear weapons switch.

**CB FCS CHAN 1** · 2-position toggle · 1 pin

Circuit breaker for flight control channel 1. Pull to open it.
**ON:** Pushed in.
**OFF:** Pulled out.

**CB FCS CHAN 2** · 2-position toggle · 1 pin

Circuit breaker for flight control channel 2.
**ON:** Pushed in.
**OFF:** Pulled out.

**CB SPD BRK** · 2-position toggle · 1 pin

Circuit breaker for the speed brake.
**ON:** Pushed in.
**OFF:** Pulled out.

**CB LAUNCH BAR** · 2-position toggle · 1 pin

Circuit breaker for the launch bar. Pulling it removes power from the launch bar system.
**ON:** Pushed in.
**OFF:** Pulled out.

**DISPENSE** · Push button · 1 pin

The large red button. Dispenses chaff and flares with the current program.

**NUC WPN** · 2-position toggle · 1 pin

**ENABLE:** Enable.
**DISABLE:** Disable.
Not modeled in DCS, so it does nothing in the sim.

## Left Vertical Panel

### LANDING GEAR

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Landing gear handle with its warning light, emergency gear extension and the gear-related switches on the left vertical panel.

**GEAR HANDLE** · 2-position toggle · 1 pin

The wheel-shaped gear handle. It cannot be raised with weight on the wheels or with the launch bar down.
**UP:** Gear up.
**DOWN:** Gear down.

**GEAR HANDLE LIGHT** · Lamp · output

Red light in the gear handle. On while the gear is moving or a main gear link is not locked.

**EMERG GEAR** · 2-position toggle · 1 pin

Emergency gear extension: the gear handle turned 90 degrees and pulled. The gear falls free and locks.
**NORM:** Handle in normal position.
**EMERG DOWN:** Handle turned and pulled.

**DOWN LOCK ORIDE** · Push button · 1 pin

Push to release the lock that stops the gear handle going up with weight on wheels.

**WARN TONE SILENCE** · Push button · 1 pin

Silences the landing gear warning tone.

**LAUNCH BAR** · 2-position toggle · 1 pin

Extends the launch bar for a catapult launch. It only extends with weight on wheels.
**EXTEND:** Launch bar down.
**RETRACT:** Launch bar up.

**FLAP** · 3-position toggle · 2 pins

Picks the flight control mode for the flaps.
**AUTO:** Flaps scheduled with angle of attack. Up on the ground.
**HALF:** Takeoff and landing flaps, up to 30 degrees, below 250 knots.
**FULL:** Full landing flaps, up to 45 degrees, below 250 knots.

**LDG/TAXI LIGHT** · 2-position toggle · 1 pin

The light on the nose gear. It only comes on with the gear handle down and the gear down.
**ON:** Light on.
**OFF:** Light off.

**ANTI SKID** · 2-position toggle · 1 pin

**ON:** Anti-skid braking, for runway landings.
**OFF:** Anti-skid off, as used on the carrier.

**HOOK BYPASS** · 2-position toggle · 1 pin

Sets how the AOA indexer behaves with the hook up. Held in FIELD by a solenoid; it drops to CARRIER when the hook comes down or power is removed.
**FIELD:** Indexer lights stay steady with the hook up.
**CARRIER:** Indexer lights flash if the hook is up.

### SELECTIVE JETTISON

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Selective jettison knob with the JETT push button in its center.

**SEL JETT** · Rotary selector · 5 pins, or 1 analog input

Picks what is jettisoned from the stations chosen with the station jettison buttons. Works with the gear up and the master arm on.
**L FUS MSL:** Left fuselage missile.
**SAFE:** Nothing selected.
**R FUS MSL:** Right fuselage missile.
**RACK/LCHR:** The stores with their racks or launchers.
**STORES:** The stores only.

**JETT** · Push button · 1 pin

Push button in the center of the knob. Jettisons what the knob and station buttons select.

### BRAKES

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Emergency and parking brake handle with the brake accumulator pressure gauge, lower left on the main instrument panel.

**BRAKE HANDLE ROTATE** · 3-position toggle, spring return · 2 pins

Turns the emergency and parking brake handle. Turn it counterclockwise and pull for the parking brake; stow it straight for the emergency brake.
**CCW:** Toward PARK.
**CW:** Back toward EMERG.

**BRAKE HANDLE PULL** · 2-position toggle · 1 pin

Pulls the emergency and parking brake handle out, or stows it.
**STOW:** Handle stowed, brakes released.
**PULL:** Handle pulled, brakes applied.

**BRAKE PRESSURE** · Needle gauge · display<br>
BRAKE ACCUMULATOR PRESSURE

Brake accumulator pressure. About 3,000 psi is normal; the red line marks 2,000 psi.

### CANOPY JETTISON

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Canopy jettison handle on the left canopy sill, just aft of the instrument panel.

**CANOPY JETT UNLOCK** · Push button · 1 pin

Unlocks the canopy jettison handle.

**CANOPY JETT** · 2-position toggle · 1 pin

Pull aft to jettison the canopy.
**PUSH:** Stowed.
**PULL:** Jettisons the canopy.

## Left Instrument Panel

### MASTER ARM

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Master mode buttons, master arm switch and emergency jettison button, top left of the instrument panel.

**A/A** · Push button · 1 pin

Selects the air-to-air master mode.

**A/A LIGHT** · Lamp · output

Air-to-air master mode selected.

**A/G** · Push button · 1 pin

Selects the air-to-ground master mode.

**A/G LIGHT** · Lamp · output

Air-to-ground master mode selected.

**MASTER ARM** · 2-position toggle · 1 pin

**ARM:** Weapons can be released or jettisoned.
**SAFE:** Weapon release is blocked.

**EMERG JETT** · Push button · 1 pin

Hold for about half a second to jettison the stores on stations 2, 3, 5, 7 and 8.

### LEFT ENGINE FIRE

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Left engine fire warning light, a guarded push button, and the fire extinguisher button with its READY and DISCH lights.

**L FIRE** · 2-position toggle · 1 pin

Guarded push button with the red FIRE light. Lift the guard and push to shut off fuel to the left engine and arm the extinguisher. Push again to open the fuel valve.
**OUT:** Normal.
**IN:** Fuel off, extinguisher armed.

**L FIRE LIGHT** · Lamp · output

Fire detected in the left engine or its accessory bay.

**FIRE EXT** · Push button · 1 pin

Discharges the fire bottle into the engine or APU whose fire button is pushed in.

**READY** · Lamp · output

The fire bottle is armed.

**DISCH** · Lamp · output

The fire bottle has been discharged.

### MASTER CAUTION

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The MASTER CAUTION light, which is also its reset button.

**MASTER CAUTION** · Push button · 1 pin

Push to reset the master caution. Also restacks the caution messages.

**MASTER CAUTION LIGHT** · Lamp · output

Comes on with any caution.

### LEFT WARNING LIGHTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Warning, caution and advisory lights on the left side of the glare shield.

**L BLEED** · Lamp · output

Bleed air leak or fire in the left engine ducting. The left bleed valve closes.

**R BLEED** · Lamp · output

Bleed air leak or fire in the right engine ducting.

**SPD BRK** · Lamp · output

The speed brake is not fully in.

**STBY** · Lamp · output

The ECM jammer is warming up.

**L BAR RED** · Lamp · output

Launch bar fault. The nose gear cannot retract.

**L BAR GREEN** · Lamp · output

Launch bar down with weight on wheels.

**REC** · Lamp · output

A threat radar is looking at you.

**XMIT** · Lamp · output

The ECM jammer is transmitting.

**GO** · Lamp · output

Countermeasures self-test passed.

**NO GO** · Lamp · output

Countermeasures self-test failed.

**ASPJ OH** · Lamp · output

The jammer is overheating.

### STATION JETTISON AND GEAR LIGHTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Station jettison select buttons over the landing gear and flap position lights.

**CTR** · 2-position toggle · 1 pin

Selects the centerline station for jettison. Lit when selected.
**OFF:** Not selected.
**ON:** Selected.

**CTR LIGHT** · Lamp · output

Centerline station selected.

**LI** · 2-position toggle · 1 pin

Selects the left inboard station.

**LI LIGHT** · Lamp · output

Left inboard station selected.

**LO** · 2-position toggle · 1 pin

Selects the left outboard station.

**LO LIGHT** · Lamp · output

Left outboard station selected.

**RI** · 2-position toggle · 1 pin

Selects the right inboard station.

**RI LIGHT** · Lamp · output

Right inboard station selected.

**RO** · 2-position toggle · 1 pin

Selects the right outboard station.

**RO LIGHT** · Lamp · output

Right outboard station selected.

**NOSE** · Lamp · output

Nose gear down and locked.

**LEFT** · Lamp · output

Left main gear down and locked.

**RIGHT** · Lamp · output

Right main gear down and locked.

**HALF** · Lamp · output

HALF flaps selected and below 250 knots.

**FULL** · Lamp · output

FULL flaps selected and below 250 knots.

**FLAPS** · Lamp · output

Flaps not where the switch asks: above 250 knots, a flap fault, spin recovery or GAIN in ORIDE.

### IFEI

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Integrated fuel and engine indicator: engine RPM, temperature, fuel flow, nozzle and oil for each engine, fuel quantity, bingo and the clock. The buttons page through it.

**MODE** · Push button · 1 pin

Two presses bring up the date and time for setting.

**QTY** · Push button · 1 pin

Steps through the tank quantities: total and internal, feed, transfer, wing, external and centerline.

**UP ARROW** · Push button · 1 pin

Raises the bingo fuel setting, or the value being set.

**DOWN ARROW** · Push button · 1 pin

Lowers the bingo fuel setting, or the value being set.

**ZONE** · Push button · 1 pin

Switches the time between local and zulu.

**ET** · Push button · 1 pin

Elapsed time: press to start, again to stop, again to resume. Hold to reset.

**IFEI BRT** · Potentiometer · 1 analog input

Display brightness. Only works with the lighting MODE switch in NITE or NVG.

### VIDEO RECORD

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Video recorder selectors on the lower left of the instrument panel.

**HMD/LDDI/RDDI** · 3-position toggle · 2 pins

Picks what one recorder channel records.
**HMD:** Helmet display.
**LDDI:** Left DDI.
**RDDI:** Right DDI.

**HUD/LDDI/RDDI** · 3-position toggle · 2 pins

Picks what the other recorder channel records.
**HUD:** Head-up display.
**LDDI:** Left DDI.
**RDDI:** Right DDI.

**REC MODE** · 3-position toggle · 2 pins

**MAN:** Records continuously.
**OFF:** Recorder off.
**AUTO:** Records when a weapon is released.

### LEFT DDI

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Left digital display indicator with its 20 push buttons and its brightness and contrast knobs.

**LDDI MODE** · Rotary selector · 3 pins, or 1 analog input

**OFF:** Display off.
**NIGHT:** Dimmer brightness range.
**DAY:** Brighter range.

**LDDI BRT** · Potentiometer · 1 analog input

Display brightness.

**LDDI CONT** · Potentiometer · 1 analog input

Display contrast.
Not modeled in DCS, so it does nothing in the sim.

**LDDI PB 1** · Push button · 1 pin

Push button 1. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 2** · Push button · 1 pin

Push button 2. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 3** · Push button · 1 pin

Push button 3. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 4** · Push button · 1 pin

Push button 4. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 5** · Push button · 1 pin

Push button 5. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 6** · Push button · 1 pin

Push button 6. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 7** · Push button · 1 pin

Push button 7. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 8** · Push button · 1 pin

Push button 8. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 9** · Push button · 1 pin

Push button 9. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 10** · Push button · 1 pin

Push button 10. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 11** · Push button · 1 pin

Push button 11. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 12** · Push button · 1 pin

Push button 12. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 13** · Push button · 1 pin

Push button 13. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 14** · Push button · 1 pin

Push button 14. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 15** · Push button · 1 pin

Push button 15. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 16** · Push button · 1 pin

Push button 16. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 17** · Push button · 1 pin

Push button 17. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 18** · Push button · 1 pin

Push button 18. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 19** · Push button · 1 pin

Push button 19. Number 1 is the lowest on the left side; the numbers run clockwise.

**LDDI PB 20** · Push button · 1 pin

Push button 20. Number 1 is the lowest on the left side; the numbers run clockwise.

## Center Instrument Panel

### AOA INDEXER

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Approach angle of attack indexer to the left of the HUD. Works with the gear down and in the air.

**AOA HIGH** · Lamp · output

Slow: angle of attack too high.

**AOA ON SPEED** · Lamp · output

On speed.

**AOA LOW** · Lamp · output

Fast: angle of attack too low.

### HUD CONTROL PANEL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

HUD symbology, brightness, video and altitude source controls under the UFC.

**REJ** · 3-position toggle · 2 pins

Removes symbology from the HUD.
**NORM:** All symbology.
**REJ 1:** Removes Mach, g, bank, the airspeed and altitude boxes and a few more.
**REJ 2:** Also removes the heading scale, range and timers.

**HUD BRT** · Potentiometer · 1 analog input

HUD symbol brightness.

**DAY/NIGHT** · 2-position toggle · 1 pin

**DAY:** Full brightness range.
**NIGHT:** Dimmer range.

**BLK LVL** · Potentiometer · 1 analog input

HUD video black level.

**VIDEO** · 3-position toggle · 2 pins

**W/B:** Video with symbology, white on black.
**VID:** Video.
**OFF:** Video off.

**BAL** · Potentiometer · 1 analog input

HUD video balance.

**AOA BRT** · Potentiometer · 1 analog input

Brightness of the AOA indexer lights.
Not modeled in DCS, so it does nothing in the sim.

**ALT** · 2-position toggle · 1 pin

**BARO:** Barometric altitude on the HUD.
**RDR:** Radar altitude on the HUD, marked R, up to 5,000 feet.

**ATT** · 3-position toggle · 2 pins

Attitude source for the HUD.
**INS:** Inertial navigation.
**AUTO:** Picks automatically.
**STBY:** Standby attitude reference.

### UFC

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Up front controller below the HUD: function buttons, option select buttons, keypad, radio volume and channel knobs, ADF switch and brightness.

**A/P** · Push button · 1 pin

Shows the autopilot modes in the option windows. Does not engage the autopilot by itself.

**IFF** · Push button · 1 pin

Shows the IFF options.

**TCN** · Push button · 1 pin

Shows the TACAN options and channel.

**ILS** · Push button · 1 pin

Shows the ILS channel and options.

**D/L** · Push button · 1 pin

Shows the datalink options.

**BCN** · Push button · 1 pin

Shows the beacon options.

**ON/OFF** · Push button · 1 pin

Turns the equipment picked with a function button on or off.

**OSB 1** · Push button · 1 pin

Option select button 1, the top one. Picks the option shown next to it.

**OSB 2** · Push button · 1 pin

Option select button 2.

**OSB 3** · Push button · 1 pin

Option select button 3.

**OSB 4** · Push button · 1 pin

Option select button 4.

**OSB 5** · Push button · 1 pin

Option select button 5, the bottom one.

**KEY 1** · Push button · 1 pin

Keypad 1.

**KEY 2** · Push button · 1 pin

Keypad 2.

**KEY 3** · Push button · 1 pin

Keypad 3.

**KEY 4** · Push button · 1 pin

Keypad 4.

**KEY 5** · Push button · 1 pin

Keypad 5.

**KEY 6** · Push button · 1 pin

Keypad 6.

**KEY 7** · Push button · 1 pin

Keypad 7.

**KEY 8** · Push button · 1 pin

Keypad 8.

**KEY 9** · Push button · 1 pin

Keypad 9.

**KEY 0** · Push button · 1 pin

Keypad 0.

**CLR** · Push button · 1 pin

Clears the scratchpad. A second press clears the option windows.

**ENT** · Push button · 1 pin

Enters the scratchpad value.

**I/P** · Push button · 1 pin

IFF identification of position.

**EMCON** · Push button · 1 pin

Stops the radar, radar altimeter and datalink transmitting.
Not modeled in DCS, so it does nothing in the sim.

**ADF** · 3-position toggle · 2 pins

Automatic direction finding on one of the radios.
**1:** Radio 1.
**OFF:** ADF off.
**2:** Radio 2.

**COMM 1 VOL** · Potentiometer · 1 analog input

Radio 1 volume. Fully counterclockwise turns radio 1 off.

**COMM 2 VOL** · Potentiometer · 1 analog input

Radio 2 volume. Fully counterclockwise turns radio 2 off.

**UFC BRT** · Potentiometer · 1 analog input

Brightness of the option and scratchpad windows.

**COMM 1 CHAN** · Potentiometer · 1 analog input

Radio 1 channel knob: channels 1 to 20, then manual, guard, cue and maritime. Turns without end, so wire an encoder.

**COMM 1 PULL** · Push button · 1 pin

Pull the radio 1 channel knob to show the channel and frequency in the scratchpad for editing.

**COMM 2 CHAN** · Potentiometer · 1 analog input

Radio 2 channel knob, the same as radio 1. Wire an encoder.

**COMM 2 PULL** · Push button · 1 pin

Pull the radio 2 channel knob to edit its channel in the scratchpad.

### AMPCD

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Center color display with its 20 push buttons, rocker switches and brightness knob, plus the heading and course set switches at its top corners.

**AMPCD BRT** · Potentiometer · 1 analog input

Turns the display on and sets its brightness.

**NGT** · Push button · 1 pin

Night brightness: automatic brightness control.

**DAY** · Push button · 1 pin

Day brightness: set with the brightness knob.

**SYM UP** · Push button · 1 pin

Sharper, dimmer symbols.

**SYM DOWN** · Push button · 1 pin

Wider, brighter symbols.

**GAIN UP** · Push button · 1 pin

Raises the video background brightness.

**GAIN DOWN** · Push button · 1 pin

Lowers the video background brightness.

**CONT UP** · Push button · 1 pin

Raises the contrast.

**CONT DOWN** · Push button · 1 pin

Lowers the contrast.

**HDG** · 3-position toggle, spring return · 2 pins

Heading set switch. Spring-loaded to the center; hold to move the heading bug.
**RIGHT:** Increase.
**LEFT:** Decrease.

**CRS** · 3-position toggle, spring return · 2 pins

Course set switch. Spring-loaded to the center; hold to move the course line.
**RIGHT:** Increase.
**LEFT:** Decrease.

**AMPCD PB 1** · Push button · 1 pin

Push button 1.

**AMPCD PB 2** · Push button · 1 pin

Push button 2.

**AMPCD PB 3** · Push button · 1 pin

Push button 3.

**AMPCD PB 4** · Push button · 1 pin

Push button 4.

**AMPCD PB 5** · Push button · 1 pin

Push button 5.

**AMPCD PB 6** · Push button · 1 pin

Push button 6.

**AMPCD PB 7** · Push button · 1 pin

Push button 7.

**AMPCD PB 8** · Push button · 1 pin

Push button 8.

**AMPCD PB 9** · Push button · 1 pin

Push button 9.

**AMPCD PB 10** · Push button · 1 pin

Push button 10.

**AMPCD PB 11** · Push button · 1 pin

Push button 11.

**AMPCD PB 12** · Push button · 1 pin

Push button 12.

**AMPCD PB 13** · Push button · 1 pin

Push button 13.

**AMPCD PB 14** · Push button · 1 pin

Push button 14.

**AMPCD PB 15** · Push button · 1 pin

Push button 15.

**AMPCD PB 16** · Push button · 1 pin

Push button 16.

**AMPCD PB 17** · Push button · 1 pin

Push button 17.

**AMPCD PB 18** · Push button · 1 pin

Push button 18.

**AMPCD PB 19** · Push button · 1 pin

Push button 19.

**AMPCD PB 20** · Push button · 1 pin

Push button 20.

### ALR-67

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Radar warning receiver control panel in the lower center of the instrument panel.

**RWR POWER** · 2-position toggle · 1 pin

Turns the radar warning receiver on and off. With power on, the legends on the panel's buttons light.
**ON:** On.
**OFF:** Off.

**POWER LIGHT** · Lamp · output

POWER legend: the receiver is on.

**DISPLAY** · Push button · 1 pin

Limits the threat display to the six highest priority emitters, marked L in the status circle. Press again to show them all.

**DISPLAY LIGHT** · Lamp · output

DISPLAY legend.

**LIMIT LIGHT** · Lamp · output

The display is limited to six emitters.

**SPECIAL** · Push button · 1 pin

Special threat display mode.

**SPECIAL LIGHT** · Lamp · output

SPECIAL legend.

**OFFSET** · Push button · 1 pin

Spreads out overlapping threat symbols on the azimuth display. Press again to undo.

**ENABLE LIGHT** · Lamp · output

Offset is on.

**OFFSET LIGHT** · Lamp · output

OFFSET legend.

**BIT** · Push button · 1 pin

Shows the current self-test status on the azimuth display.

**BIT LIGHT** · Lamp · output

BIT legend.

**FAIL LIGHT** · Lamp · output

The periodic self-test found a failure.

**DMR** · Potentiometer · 1 analog input

Brightness of the lights on this panel.

**AUDIO** · Potentiometer · 1 analog input

Audio level.
Not modeled in DCS, so it does nothing in the sim.

**DIS TYPE** · Rotary selector · 5 pins, or 1 analog input

Which threat type gets display priority, shown in the status circle.
**N:** Normal.
**I:** Air intercept radars.
**A:** Anti-aircraft artillery.
**U:** Unknown emitters.
**F:** Friendly emitters.

### DISPENSER AND ECM JETT

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Countermeasures dispenser switch and the ECM jettison button.

**DISPENSER** · 3-position toggle · 2 pins

**BYPASS:** Bypasses the programs: the throttle dispense switch releases two chaff forward, two flares aft.
**ON:** Programs available after a five second self-test.
**OFF:** Dispenser off.

**ECM JETT** · 2-position toggle · 1 pin

Releases all chaff and flares on board. Works only in the air, and lights when pressed.
**OFF:** Out.
**ON:** Pushed.

**ECM JETT LIGHT** · Lamp · output

ECM jettison selected.

### ECM

*Draft: generated from the simulator, not yet checked against a real cockpit.*

ALQ-165 jammer mode switch.

**ECM MODE** · Rotary selector · 5 pins, or 1 analog input

**OFF:** Jammer off.
**STBY:** Warming up; the STBY light is on for about five minutes.
**BIT:** Self-test.
**REC:** Receive only.
**XMIT:** Jams threats.

**AUX REL** · 2-position toggle · 1 pin

Auxiliary release.
**ENABLE:** Enabled.
**NORM:** Normal.

### LOWER INSTRUMENTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The cabin pressure altimeter and the standby clock.

**CABIN ALT** · Needle gauge · display<br>
CABIN PRESSURE ALTIMETER

Cockpit pressure altitude, 0 to 50,000 feet.

**CLOCK** · Aircraft clock · display<br>
STANDBY CLOCK

Time of day with an elapsed time function.

**hour hand** · Needle · 0 to 12 · 4 pins when physical

**elapsed minutes** · Needle · 0 to 60 · 4 pins when physical

**elapsed seconds** · Needle · 0 to 60 · 4 pins when physical

**minute hand** · Needle · 0 to 60 · 4 pins when physical

## Right Instrument Panel

### LOCK SHOOT

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Lock and shoot lights on the canopy bow above the HUD.

**LOCK** · Lamp · output

Radar is tracking a single target inside maximum range.

**SHOOT** · Lamp · output

Weapon release conditions are met. Flashes inside no-escape range.

**SHOOT STROBE** · Lamp · output

Flashes with a valid shot.

### RIGHT ENGINE AND APU FIRE

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Right engine fire warning light and the APU fire light, both push buttons.

**R FIRE** · 2-position toggle · 1 pin

Guarded push button with the red FIRE light. Lift the guard and push to shut off fuel to the right engine and arm the extinguisher.
**OUT:** Normal.
**IN:** Fuel off, extinguisher armed.

**R FIRE LIGHT** · Lamp · output

Fire detected in the right engine bay.

**APU FIRE** · 2-position toggle · 1 pin

Push to shut off the APU and arm the extinguisher for it.
**OUT:** Normal.
**IN:** APU fuel off, extinguisher armed.

**APU FIRE LIGHT** · Lamp · output

Fire detected in the APU bay.

### RIGHT WARNING LIGHTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Recorder, dispenser and threat warning lights on the right side of the glare shield.

**RCDR ON** · Lamp · output

The video recorder is running.

**DISP** · Lamp · output

A dispense program is ready for the detected threat and waits for your consent.

**SAM** · Lamp · output

A surface-to-air missile radar is locked on.

**AI** · Lamp · output

A hostile air intercept radar is locked on.

**AAA** · Lamp · output

A radar-directed anti-aircraft gun is tracking.

**CW** · Lamp · output

A continuous wave radar, probably guiding a missile.

### RIGHT DDI

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Right digital display indicator, the same as the left one.

**RDDI MODE** · Rotary selector · 3 pins, or 1 analog input

**OFF:** Display off.
**NIGHT:** Dimmer brightness range.
**DAY:** Brighter range.

**RDDI BRT** · Potentiometer · 1 analog input

Display brightness.

**RDDI CONT** · Potentiometer · 1 analog input

Display contrast.
Not modeled in DCS, so it does nothing in the sim.

**RDDI PB 1** · Push button · 1 pin

Push button 1.

**RDDI PB 2** · Push button · 1 pin

Push button 2.

**RDDI PB 3** · Push button · 1 pin

Push button 3.

**RDDI PB 4** · Push button · 1 pin

Push button 4.

**RDDI PB 5** · Push button · 1 pin

Push button 5.

**RDDI PB 6** · Push button · 1 pin

Push button 6.

**RDDI PB 7** · Push button · 1 pin

Push button 7.

**RDDI PB 8** · Push button · 1 pin

Push button 8.

**RDDI PB 9** · Push button · 1 pin

Push button 9.

**RDDI PB 10** · Push button · 1 pin

Push button 10.

**RDDI PB 11** · Push button · 1 pin

Push button 11.

**RDDI PB 12** · Push button · 1 pin

Push button 12.

**RDDI PB 13** · Push button · 1 pin

Push button 13.

**RDDI PB 14** · Push button · 1 pin

Push button 14.

**RDDI PB 15** · Push button · 1 pin

Push button 15.

**RDDI PB 16** · Push button · 1 pin

Push button 16.

**RDDI PB 17** · Push button · 1 pin

Push button 17.

**RDDI PB 18** · Push button · 1 pin

Push button 18.

**RDDI PB 19** · Push button · 1 pin

Push button 19.

**RDDI PB 20** · Push button · 1 pin

Push button 20.

### IR COOL AND HMD

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Sidewinder seeker cooling switch and the helmet display brightness knob.

**IR COOL** · 3-position toggle · 2 pins

Cooling for the Sidewinder seekers.
**ORIDE:** Cools all seekers now.
**NORM:** Cools the selected missile.
**OFF:** No cooling.

**HMD** · Potentiometer · 1 analog input

Turns the helmet display on and sets its brightness.

### SPIN RECOVERY

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Guarded spin recovery switch and the SPN light. The real jet's manuals forbid using it; DCS models it anyway.

**SPIN** · 2-position toggle · 1 pin

Guarded. Puts the flight controls into spin recovery mode.
**NORM:** Spin recovery engages by itself when its conditions are met.
**RCVY:** Spin recovery mode whenever the airspeed is about 120 knots.

**SPN** · Lamp · output

Spin recovery mode.

### STANDBY INSTRUMENTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Standby attitude reference, airspeed, altimeter and vertical velocity indicators with their knobs.

**SARI** · Standby ADI · display<br>
STANDBY ATTITUDE REFERENCE INDICATOR

Self-contained gyro for pitch and roll, with a turn needle and slip ball below. An OFF flag shows when it loses power or is caged.

**pitch** · Needle · -1.5708 to 1.5708 · 4 pins when physical

**bank** · Needle · -3.14159 to 3.14159 · 4 pins when physical

**horizontal pointer** · Needle · -1 to 1 · 4 pins when physical

**miniature airplane** · Needle · 0 to 1 · 4 pins when physical

**slip ball** · Needle · -1 to 1 · 4 pins when physical

**turn needle** · Needle · -4.5 to 4.5 · 4 pins when physical

**vertical pointer** · Needle · -1 to 1 · 4 pins when physical

**SAI CAGE** · Push button · 1 pin

Pull to cage the standby attitude indicator.

**SAI PITCH ADJ** · Potentiometer · 1 analog input

Turn the cage knob to set the zero-pitch mark. Wire an encoder.

**SAI TEST** · Push button · 1 pin

Tests the standby attitude indicator.

**STBY AIRSPEED** · Needle gauge · display<br>
STANDBY AIRSPEED INDICATOR

Indicated airspeed, 60 to 850 knots, straight from the left pitot.

**STBY ALTIMETER** · Altimeter · display<br>
STANDBY ALTIMETER

Barometric altitude. The pointer turns once per 1,000 feet and the drum reads thousands. The window shows the pressure setting, set with ALT SET.

**100 ft pointer** · Needle · 0 to 1000 · 4 pins when physical

**pressure drum, last digit** · Needle · 0 to 10 · 4 pins when physical

**pressure drum, middle digit** · Needle · 0 to 10 · 4 pins when physical

**pressure drum, first digits** · Needle · 26 to 31 · 4 pins when physical

**10,000 ft drum** · Needle · 0 to 9 · 4 pins when physical

**1,000 ft drum** · Needle · -1 to 10 · 4 pins when physical

**ALT SET** · Potentiometer · 1 analog input

Altimeter setting knob. Also feeds the air data computer. Wire an encoder.

**STBY VVI** · VVI · display<br>
STANDBY VERTICAL VELOCITY INDICATOR

Rate of climb or descent, up to 6,000 feet per minute.

### RWR AZIMUTH INDICATOR

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Brightness knob of the threat azimuth display on the right side of the instrument panel.

**RWR BRT** · Potentiometer · 1 analog input

Brightness of the threat display.

## Right Vertical Panel

### ARRESTING HOOK

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Arresting hook handle with the HOOK light.

**HOOK** · 2-position toggle · 1 pin

**UP:** Hook up.
**DOWN:** Hook down for an arrested landing.

**HOOK LIGHT** · Lamp · output

The hook is moving or is not where the handle says.

### WING FOLD

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Wing fold handle: pull it out, then turn it to fold or spread the outer wings.

**WING FOLD** · Rotary selector · 3 pins, or 1 analog input

Turns the pulled-out handle.
**FOLD:** Folds the wings.
**HOLD:** Stops them where they are.
**SPREAD:** Spreads the wings.

**WING FOLD PULL** · 2-position toggle · 1 pin

Pull the handle out before turning it; push it in to lock spread wings.
**STOW:** Pushed in.
**PULL:** Pulled out.

### RADAR ALTIMETER

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Radar altitude indicator, 0 to 5,000 feet, with its low altitude warning.

**RADAR ALT** · Needle gauge · display<br>
RADAR ALTITUDE

Height above the ground or water from 0 to 5,000 feet.

**altitude pointer** · Needle · -10 to 5100 ft · 4 pins when physical

**low altitude index** · Needle · -0.03 to 1 ft · 4 pins when physical

**RADALT SET** · Potentiometer · 1 analog input

Turn clockwise to switch it on and set the low altitude warning. Wire an encoder.

**RADALT BIT** · Push button · 1 pin

Push the knob to test the radar altimeter.

**LOW ALT** · Lamp · output

Below the low altitude warning setting.

**RADALT GREEN** · Lamp · output

Built-in test light.

### HYDRAULIC PRESSURE

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Hydraulic pressure for system 1 (left) and system 2 (right).

**HYD PRESS** · Needle gauge · display<br>
HYDRAULIC PRESSURE

System 1 powers only the flight controls; system 2 also runs the speed brake and the other hydraulic parts.

**system 1** · Needle · 0 to 5000 psi · 4 pins when physical

**system 2** · Needle · 0 to 5000 psi · 4 pins when physical

### CAUTION LIGHTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The yellow caution lights on the right vertical panel.

**CK SEAT** · Lamp · output

The ejection seat is not armed.

**APU ACC** · Lamp · output

APU accumulator pressure too low to start.

**BATT SW** · Lamp · output

Battery switch ON.

**FCS HOT** · Lamp · output

Flight control computers are not cooled enough. Try AV COOL EMERG.

**GEN TIE** · Lamp · output

GEN TIE switch in RESET.

**FUEL LO** · Lamp · output

Less than 800 pounds in a feed tank.

**FCES** · Lamp · output

A flight control function has been lost.

**L GEN** · Lamp · output

Left generator off or failed.

**R GEN** · Lamp · output

Right generator off or failed.

### AV COOL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Avionics cooling switch.

**AV COOL** · 2-position toggle · 1 pin

**NORM:** Normal avionics cooling.
**EMERG:** Emergency cooling, used with FCS HOT.
DCS flips this switch on each press, so the manager presses it only when the sim and the panel disagree.

## Right Console

### ELECTRICAL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Battery and generator switches with the battery voltmeter.

**BATT** · 3-position toggle · 2 pins

**ON:** Batteries connect automatically when the bus voltage drops.
**OFF:** Batteries charge but do not connect.
**ORIDE:** Connects the emergency battery regardless of the utility battery.

**L GEN** · 2-position toggle · 1 pin

**NORM:** Left generator on.
**OFF:** Left generator off.

**R GEN** · 2-position toggle · 1 pin

**NORM:** Right generator on.
**OFF:** Right generator off.

**VOLTMETER** · Needle gauge · display<br>
BATTERY VOLTMETER

Utility and emergency battery voltage, 16 to 30 volts. Both needles sit at 16 with the battery switch OFF.

**utility battery** · Needle · 16 to 30 V · 4 pins when physical

**emergency battery** · Needle · 16 to 30 V · 4 pins when physical

### ECS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Environmental control: bleed air source, cooling and pressurization modes, cabin and suit temperature, engine anti-ice and pitot heat.

**BLEED AIR** · Rotary selector · 4 pins, or 1 analog input

Where the air conditioning takes its air from.
**R OFF:** Left engine only.
**NORM:** Both engines.
**L OFF:** Right engine only.
**OFF:** No engine bleed air; ram air is used instead.

**AUG PULL** · Push button · 1 pin

Pull the bleed air knob to let the APU add air on the ground at low power.

**ECS MODE** · 3-position toggle · 2 pins

**AUTO:** Automatic temperature control.
**MAN:** Manual temperature control.
**OFF/RAM:** Air conditioning off, ram air.

**CABIN PRESS** · 3-position toggle · 2 pins

**NORM:** Normal pressurization.
**DUMP:** Dumps cabin pressure.
**RAM/DUMP:** Dumps pressure and brings in ram air.

**CABIN TEMP** · Potentiometer · 1 analog input

Cabin temperature.

**SUIT TEMP** · Potentiometer · 1 analog input

Anti-exposure suit temperature.

**ENG ANTI ICE** · 3-position toggle · 2 pins

**ON:** Hot air through the engine inlets.
**OFF:** Off.
**TEST:** Triggers the ice caution to test it.

**PITOT HEAT** · 2-position toggle · 1 pin

**ON:** Heaters on whenever there is power.
**AUTO:** Heaters on in the air.
DCS flips this switch on each press, so the manager presses it only when the sim and the panel disagree.

### DEFOG

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Windshield defog handle and windshield anti-ice and rain switch.

**DEFOG** · Potentiometer · 1 analog input

Blows warm air on the canopy and windshield.

**WINDSHIELD** · 3-position toggle · 2 pins

**ANTI ICE:** Hot air on the windshield.
**OFF:** Off.
**RAIN:** Rain removal.

### INTERIOR LIGHTS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Interior lighting: console, instrument, flood, chart and warning light brightness, the lighting mode and the lights test.

**CONSOLES** · Potentiometer · 1 analog input

Console and circuit breaker panel lighting, from OFF to BRT.

**INST PNL** · Potentiometer · 1 analog input

Instrument panel, UFC and vertical panel lighting.

**FLOOD** · Potentiometer · 1 analog input

White flood lights. No effect in NVG.

**CHART** · Potentiometer · 1 analog input

Chart light on the canopy arch.

**WARN/CAUT** · Potentiometer · 1 analog input

Brightness of the warning, caution and advisory lights in their low range.

**MODE** · 3-position toggle · 2 pins

**DAY:** Full brightness.
**NITE:** Dimmer warning lights.
**NVG:** Night vision goggle lighting: dim warning lights, console flood lights.

**LT TEST** · 2-position toggle · 1 pin

Tests the warning, caution and advisory lights, the AOA indexer and the IFEI.
**TEST:** Test.
**OFF:** Normal.
DCS flips this switch on each press, so the manager presses it only when the sim and the panel disagree.

### SENSORS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Sensor power: radar, inertial navigation, targeting pod, laser and laser spot tracker.

**RADAR** · Rotary selector · 4 pins, or 1 analog input

Radar power.
**OFF:** Radar off.
**STBY:** Warming up, no transmitting.
**OPR:** Operating.
**EMERG:** Operates with the safety interlocks bypassed. Pull the knob to reach it.

**INS** · Rotary selector · 8 pins, or 1 analog input

Inertial navigation mode.
**OFF:** Off.
**CV:** Carrier alignment.
**GND:** Ground alignment.
**NAV:** Navigating.
**IFA:** In-flight alignment.
**GYRO:** Gyro mode.
**GB:** Gyrocompass backup.
**TEST:** Test.

**FLIR** · 3-position toggle · 2 pins

Targeting pod power.
**ON:** Pod on.
**STBY:** Standby, the detector cools down.
**OFF:** Pod off.

**LTD/R** · 2-position toggle · 1 pin

Lever-locked laser switch. Held in ARM by a magnet when everything else is ready.
**ARM:** Laser can fire.
**SAFE:** Laser blocked.

**LST/NFLR** · 2-position toggle · 1 pin

**ON:** Laser spot tracker on.
**OFF:** Off.

### KY-58

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Secure voice panel.

**KY-58 MODE** · Rotary selector · 4 pins, or 1 analog input

**P:** Plain.
**C:** Cipher.
**LD:** Load.
**RV:** Receive variable.

**KY-58 VOL** · Potentiometer · 1 analog input

Secure voice volume.

**KY-58 FILL** · Rotary selector · 8 pins, or 1 analog input

Picks the fill position for the keys.

**KY-58 POWER** · Rotary selector · 3 pins, or 1 analog input

**OFF:** Off.
**ON:** On.
**TD:** Time delay.

### RIGHT WALL

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The right cockpit wall: canopy switch, FCS BIT switch and circuit breakers.

**CANOPY** · 3-position toggle, spring return · 2 pins

Spring-loaded to HOLD from CLOSE.
**OPEN:** Raises the canopy.
**HOLD:** Stops it.
**CLOSE:** Lowers and locks it.

**FCS BIT** · Push button · 1 pin

Hold while pressing FCS RESET to start the flight control self-test.

**CB FCS CHAN 3** · 2-position toggle · 1 pin

Circuit breaker for flight control channel 3.
**ON:** Pushed in.
**OFF:** Pulled out.

**CB FCS CHAN 4** · 2-position toggle · 1 pin

Circuit breaker for flight control channel 4.
**ON:** Pushed in.
**OFF:** Pulled out.

**CB HOOK** · 2-position toggle · 1 pin

Circuit breaker for the arresting hook.
**ON:** Pushed in.
**OFF:** Pulled out.

**CB LG** · 2-position toggle · 1 pin

Circuit breaker for the landing gear.
**ON:** Pushed in.
**OFF:** Pulled out.

## Stick and Throttle

### STICK

*Draft: generated from the simulator, not yet checked against a real cockpit.*

The control stick controls DCS lets you click. The rest of the stick is bound as joystick buttons in DCS.

**WPN REL** · Push button · 1 pin

Air-to-ground weapon release button.

**RECCE** · Push button · 1 pin

Reconnaissance event mark.

**UNDESIG/NWS** · Push button · 1 pin

Undesignates a target, or toggles nosewheel steering on the ground.

**PADDLE** · Push button · 1 pin

Disengages the autopilot and nosewheel steering while held.

### THROTTLE

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Throttle controls DCS lets you click: the exterior lights master switch and the friction lever.

**EXT LT** · 2-position toggle · 1 pin

Exterior lights master switch.
**ON:** Exterior lights work.
**OFF:** All off.

**FRICTION** · Potentiometer · 1 analog input

Throttle friction lever.

## Seat and Other

### EJECTION SEAT

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Ejection seat handles and adjustments.

**SEAT ARM** · 2-position toggle · 1 pin

Seat safe and arm handle.
**ARMED:** Seat armed.
**SAFE:** Seat safe.

**EJECT** · Push button · 1 pin

Ejection handle. DCS needs three pulls.

**MAN ORIDE** · 2-position toggle · 1 pin

Manual override handle.
**PULL:** Pulled.
**PUSH:** Stowed.

**HARNESS** · 2-position toggle · 1 pin

Shoulder harness lock.
**LOCK:** Locked.
**UNLOCK:** Free.

**SEAT HEIGHT** · 3-position toggle, spring return · 2 pins

Spring-loaded to the center.
**UP:** Seat up.
**HOLD:** Stop.
**DOWN:** Seat down.

### MISCELLANEOUS

*Draft: generated from the simulator, not yet checked against a real cockpit.*

Cockpit controls that belong to no panel: rudder pedal adjustment, air vents and the video sensor tests.

**RUDDER PEDAL ADJ** · Push button · 1 pin

Unlocks the rudder pedals so they can be moved.

**LEFT LOUVER** · Potentiometer · 1 analog input

Left air vent.

**RIGHT LOUVER** · Potentiometer · 1 analog input

Right air vent.

**L VIDEO BIT** · Push button · 1 pin

Starts the left video sensor self-test.

**R VIDEO BIT** · Push button · 1 pin

Starts the right video sensor self-test.

**HUD VIDEO BIT** · Push button · 1 pin

Starts the HUD video self-test.
