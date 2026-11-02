# OMEGA-50

Six-voice polysynth plugin, with a free editor for the hardware it is modeled on.

<img width="1944" height="1271" alt="OMEGA-50 100 screen 150pr" src="https://github.com/user-attachments/assets/0e11f263-c709-4470-8159-a972714a2c39" />

OMEGA-50 is a six-voice polyphonic synthesizer modeled on the Roland MKS-50, the rack version of the
Alpha Juno: pulse, sawtooth, sub-oscillator and noise into a high-pass and a resonant low-pass filter,
one envelope, one LFO and the stereo chorus, with the 64 factory tones. Every parameter sits on its
own knob in our own panel, with a live drawing of the envelope.

## The plugin

VST3 and AU, for Windows and macOS. Available at
**[ravegeneration.io](https://ravegeneration.io/products/rave-generation-omega-50)**.

- **A faithful recreation.** The MKS-50's voice, its envelopes and its chorus, checked against
  recordings of a real unit.
- **Every parameter on a knob.** All 36 tone parameters on one panel in their sections, with each
  waveform's shape drawn in its window.
- **Live envelope display.** The envelope drawn as you set it, with its times, levels and key on and
  key off marked. One click hides it or its labels.
- **Poly, chord and mono.** Six voices, 16 chords played from a single key, or mono with its own bend
  range, and portamento.
- **Played by your controller.** Velocity, aftertouch, mod wheel and pitch bend, each with its depth
  on the panel, and the sustain pedal.
- **Stereo chorus.** On or off with one click, with its own rate.

In this repository:

| File | What it is |
|---|---|
| [OMEGA-50UserManual.pdf](OMEGA-50UserManual.pdf) | The user manual |
| [OMEGA-50-Presets.zip](OMEGA-50-Presets.zip) | The 64 factory tones as presets |

## The editor

A free patch editor for the hardware. It opens OMEGA-50 presets too, so a sound made in the plugin
can go to a real unit.

### Run it

**[omega50.re-style.nl](https://omega50.re-style.nl)** opens it in the browser. No install, no account.

### Download

| Platform | File | Size |
|---|---|---|
| Windows | [Setup OMEGA-50 Editor v1.0.0.exe](https://omega50.re-style.nl/Setup%20OMEGA-50%20Editor%20v1.0.0.exe) | 114 MB |
| macOS | [Setup OMEGA-50 Editor v1.0.0.dmg](https://omega50.re-style.nl/Setup%20OMEGA-50%20Editor%20v1.0.0.dmg) | 229 MB, universal |

The macOS build is universal, so Apple Silicon and Intel both. It is the same editor in every case.

### What it does

- **Every tone parameter on a knob.** LFO, DCO, Key, Waveforms, Voice, VCF, VCA, Env, Chorus and
  Bender, laid out like the plugin.
- **Opens what you already have.** A .syx file (a tone, a tone or patch bank, or the chord memories),
  or a sound saved as an OMEGA-50 .preset, a .talalpha or a .repatch. Load it, drop it or paste it.
- **Banks.** Store the current sound or patch settings in a bank slot, then save the tone, the bank or
  the chord memories as .syx.
- **Sends to the unit.** A single tone, a whole bank of 64 tones or 64 patches, or the 16 chord
  memories, over MIDI, with your own choice of MIDI in, out and channel.
- **Keeps your work.** Leaving with a bank that is not saved or sent asks first.

## Hardware

### MKS-50 and Alpha Juno

The editor talks to the unit over MIDI with SysEx. To receive a whole bank, set the unit to Memory
Protect off and Bulk*Load, pick the group (T-a or T-b for tones, P-A or P-B for patches, CM for the
chord memories), then Write. Sending a bank replaces the 64 tones or patches of that group, so back
up the unit's own bank first if you want to keep it.

## Browser support

Chrome or Edge for the MIDI features, which is a Web MIDI limitation rather than a choice. Safari has
no Web MIDI at all, so on a Mac use the desktop app or a Chromium browser.

## First run

The macOS build is signed and notarised, so it opens normally.

The Windows installer is not signed, so SmartScreen shows "Windows protected your PC". Click More
info, then Run anyway.

## License

The plugin is sold at [ravegeneration.io](https://ravegeneration.io/products/rave-generation-omega-50)
under the Rave Generation EULA.

The editor is free to use, privately or commercially, on as many machines as you like. It is not open
source: please link to the download rather than re-hosting it.

## Credits

Built by [Rave Generation](https://ravegeneration.io).

Roland, MKS-50 and Alpha Juno are trademarks of Roland Corporation. TAL-Pha is a product of TAL
Software GmbH. This project is not affiliated with, endorsed by, or sponsored by any of them.
