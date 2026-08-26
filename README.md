# SKETCH-303

Pattern editor for the Roland TB-303 and the Behringer TD-3.

![SKETCH-303 in the silver and the dark theme](https://303.re-style.nl/sketch303_light_dark.png)

A piano roll instead of sixteen step buttons, a generator for when the blank grid stares back,
TR-909 shuffle measured from hardware, and an acid voice built in so it works with nothing plugged
in. Over MIDI it plays either machine, records a 303's own sequencer back into the grid, and moves
patterns in and out of a TD-3's memory slots.

## Run it

**[303.re-style.nl](https://303.re-style.nl)** opens it in the browser. No install, no account, and
it keeps working offline once the page has loaded.

Chrome and Edge show an Install icon in the address bar, which gives it its own window.

## Download

| Platform | File | Size |
|---|---|---|
| Windows | [Setup SKETCH-303 v1.0.0.exe](https://303.re-style.nl/Setup%20SKETCH-303%20v1.0.0.exe) | 115 MB |
| macOS | [Setup SKETCH-303 v1.0.0.dmg](https://303.re-style.nl/Setup%20SKETCH-303%20v1.0.0.dmg) | 229 MB, universal |
| Both, plus the manual | [Sketch-303Setup.zip](https://303.re-style.nl/Sketch-303Setup.zip) | 344 MB |

The macOS build is universal, so Apple Silicon and Intel both. It is the same app in every case.
Patterns are stored per install, so a bank saved in the browser is not visible to the desktop app:
use **Save all 16** in one and **Load preset** in the other to move them across.

## What it does

- **Piano roll.** Left-click places a note, right-click removes it, drag paints a run. Accent, slide
  and tie get their own lanes under the grid.
- **Generator.** Five sliders plus key and scale. Pitches follow a bounded random walk over scale
  degrees, so a roll comes out as a line with shape. Mutate rerolls a quarter of the steps. Five Feel
  presets set the sliders and roll in one click.
- **TR-909 shuffle.** Seven settings matching the 909's Main Keys 1 to 7, derived from rimshot
  recordings off a real machine. Key 5 lands on 2:1, key 7 on 3:1, and the bar never drifts.
- **Built-in acid voice.** Sawtooth into a resonant low-pass with an envelope that multiplies the
  cutoff rather than adding to it. Slides glide without retriggering. Runs with no hardware at all.
- **Presets and export.** Sixteen slots, saved one at a time or as a whole bank. Export .mid writes a
  standard MIDI file with the shuffle already in the timing and slides as overlapping notes.
- **MIDI monitor.** Every byte in and out, decoded. Notes by name and velocity, CCs by function,
  SysEx read against the settings table.

## Hardware

<img src="https://303.re-style.nl/sketch303_gear.jpg" width="400"
     alt="A Behringer TD-3 and a Roland TB-303 in a studio rack">

*The two machines this was built for.*

### Roland TB-303

Needs a [Sequentix MIDIBass 303](https://www.sequentix.com/products/midibass-303-kit) retrofit
fitted. With it the editor plays the machine, and all twelve of the unit's EEPROM settings are
writable from one panel.

A TB-303 has no pattern memory a computer can reach, so **Capture** records what the machine
transmits instead. It counts the 303's own MIDI clock at six ticks per step and anchors on MIDI
Start, so a pattern beginning with a rest still lines up. Pitch, accent, slide and tie all survive.

### Behringer TD-3 and TD-3-MO

Nothing to fit. Pick a group, section and pattern, read the slot, edit it, flash it back. Writing is
read-modify-write, so bytes the format still lists as unknown are carried through untouched. A read
of the same slot is required before flashing, which is also how you take a backup.

Accent travels as velocity on both machines, and slide as overlapping notes, so the hardware makes
the slide itself. A standard TD-3 has no MIDI route to its filter. A TD-3-MO follows CC74.

## Browser support

Chrome or Edge for the MIDI features, which is a Web MIDI limitation rather than a choice. Safari has
no Web MIDI at all, so on a Mac use the desktop app or a Chromium browser. Editing, the acid voice,
the generator, shuffle and .mid export need no hardware, no interface and no network.

## Manual

[SKETCH-303UserManual.pdf](SKETCH-303UserManual.pdf) in this repository, or
[read it online](https://303.re-style.nl/manual.html). It is also inside the app, under the Manual
button next to About.

## First run

The macOS build is signed and notarised, so it opens normally.

The Windows installer is not signed, so SmartScreen shows "Windows protected your PC". Click More
info, then Run anyway.

## License

Free to use, privately or commercially, on as many machines as you like. Anything you make with it
is yours, with no credit required. It is not open source: please link to the download rather than
re-hosting it. See [LICENSE](LICENSE).

## Credits

Built by [Rave Generation](https://ravegeneration.io).

TB-303, TR-909 and Roland are trademarks of Roland Corporation. TD-3 and Behringer are trademarks of
Music Tribe. MIDIBass 303 is a product of Sequentix GmbH. This project is not affiliated with,
endorsed by, or sponsored by any of them.
