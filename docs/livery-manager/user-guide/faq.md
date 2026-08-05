# FAQ

## I installed a livery but it doesn't show up in DCS

Almost always one of these, in order of likelihood:

1. **DCS was running when you installed.** The game only scans for liveries
   at startup. **Fully close DCS** (not just back to the main menu) and
   launch it again.
2. **Wrong aircraft.** If the manager flagged the livery with a yellow
   *Check the aircraft* warning and the guess was wrong, it's sitting in
   another aircraft's folder. Find it on the Library page, remove it, and
   reinstall with the right aircraft selected.
3. **Country restriction.** Some liveries are restricted to specific
   countries by their author. In the mission editor, set the aircraft's
   country to match (or ask the author for an unrestricted version).

## Will other players see my livery in multiplayer?

Only if they have the **same livery installed**; skins are client-side.
Everyone else sees the aircraft's default livery. Squadrons typically share a
livery pack so everyone sees the same paint.

## Will this get me kicked by integrity check?

No. Liveries in `Saved Games` are exactly where DCS wants user content, and
multiplayer integrity check doesn't inspect them. IC problems come from
modified files **inside the game installation**, which this manager never
touches.

## What archive formats work?

`.zip` out of the box. `.7z` and `.rar` are extracted with
[7-Zip](https://www.7-zip.org/) when it's installed; the manager tells you
if it's needed. Archives containing further archives are unpacked
automatically.

## Do my liveries survive DCS updates?

Yes. Updates and repairs only touch the game installation; your
`Saved Games\...\Liveries` folder is yours. The same goes for uninstalling
the Livery Manager; your collection stays.

## Liveries are huge. Where did my disk space go?

High-resolution skins routinely run to hundreds of MB each. The Library page
shows the size of every livery, every aircraft group, and the collection
total, so the space hogs are easy to spot and remove.

## Can I still install liveries by hand?

Of course. Anything you copy into the Liveries folder yourself shows up in
the Library marked **Manual**. The manager never overwrites or deletes manual
liveries without an explicit confirmation.

## Where can I get liveries?

The [DCS User Files](https://www.digitalcombatsimulator.com/en/files/?set_filter=Y&arrFilter_pf%5Bfiletype%5D=6)
section has tens of thousands, filterable by aircraft. There's a shortcut to
it on the manager's Settings page.
