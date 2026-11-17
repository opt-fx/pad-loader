# MKSREC 1 Pad Loader

A browser tool for the MKSREC 1 sampler. It does three things:

- **Loads samples onto the sampler's 64 pads** and saves a fresh `.mks` project ready to copy to the card. Apart from the sounds, their outputs, voices and filter modes, and a few project settings, the project matches a brand-new one from the sampler, so tuning, loops, envelopes and the rest stay at the defaults for you to set on the hardware.
- **Imports SP-1200 kits onto pads**, from a Rossum `.sp12` project or an original SP-1200 floppy image (`.hfe`), with their names, outputs, tuning and decay.
- **Converts Rossum `.sp12` projects to `.hfe` floppy images**, so the sampler can import a whole kit, sequences and songs included.

The whole app is one HTML file and runs in the browser with no install. Nothing is uploaded anywhere: your sounds stay on your computer. Made by OPT.

**Use it now: https://opt-fx.github.io/mksrec1-pad-loader/**

**Status: version 1.0.** Saved projects, SP-1200 imports and converted floppies have all loaded correctly on an MKSREC 1. SP-1200 imports match the sampler's own conversion of the same floppies sample for sample.

## Quick start

1. Open the app's page, or download `index.html` and open it from disk, in Chrome, Edge or Firefox.
2. Drop audio files onto a pad. Several files fill the pads that follow, in name order.
3. Set each pad's output if you need to (see Outputs).
4. Type a file name and press **Save .mks**.
5. Copy the file into the card's `/Songs` folder and load it on the sampler in Disk mode.

## Loading sounds

- **Audio files.** WAV, AIFF, MP3, FLAC and OGG. Audio is converted the way the sampler converts WAVs: left channel only, resampled to 26,040 Hz. Each sound is named from the first six characters of its file name; click the name to change it.
- **Conversion.** The sampler's import modes are available: clean, 12b, 8b, 8b ul, 6b and 6b ul. Set the mode for new sounds in the toolbar, or change it per pad. The original audio is kept, so you can switch modes and listen to the difference. 12b d and gleam are not reproduced; load the WAV on the sampler for those.
- **Length.** The memory bar shows how much of the sampler's 832 seconds is used. Sounds longer than the 13 seconds the sampler records are marked.

## SP-1200 kits

SP-1200 kits can be imported from a Rossum SP-1200 `.sp12` project or from an original SP-1200 floppy image (`.hfe`). Each kit comes in with its sounds, names, outputs, tuning and decay mode, the same as when the sampler converts a floppy itself. Each sound keeps the SP-1200's 12-bit data with nothing added.

- **Import SP-1200…** puts a kit into the first banks where it overwrites nothing, so several kits can share one project.
- **Drop a `.sp12` or `.hfe` file on a pad** to start the kit at that pad's bank.
- Pads that still carry an SP-1200 default name such as `A1` are named after the kit, for example `m808A1`.

## Converting .sp12 to .hfe

The sampler imports SP-1200 floppy images (`.hfe`) in full, with sequences and songs, but cannot read Rossum `.sp12` projects. **.sp12 → .hfe…** converts a `.sp12` into a floppy image; put it on the card and load it in Disk mode (highlight it, press **0**, then **9**). It does not touch the project in the pad loader.

- The kit's sounds, settings, sequences and songs are carried across unchanged.
- The disk holds no SP-1200 operating system: the sampler does not need it.
- A Rossum has twice the SP-1200's sample memory. A kit stored in the Rossum-only memory is moved into the floppy's memory when it fits. A kit that needs more than a floppy's memory (4 of the Rossum's 8 memory pages, about 10 s) is refused. Its sounds can still go onto pads with **Import SP-1200…**, without its sequences; or remove sounds on the Rossum until it fits.
- Checked on the sampler with the factory TechnoDrums and Congas kits and a kit made on a Rossum.

## Outputs

Each pad goes to one of the sampler's eight outputs: 1–2 have the dynamic filters, 3–6 the static low-pass filters and 7–8 are clean. Set the selected pad's output with the 1–8 buttons or number keys, or drag a pad onto an output in the outputs panel. Hover over an output to see its pads. **Pad n → output n** and **Defaults** set every pad at once.

The output is set as Setup 17 sets it.

## Project settings

Written into every project you save, and remembered in the browser:

- **Choke groups off** (on by default). A brand-new project from the sampler puts every odd pad in choke group 7 and every even pad in group 8, so any odd pad cuts off any other odd pad. With this on, every pad is saved with no choke group (`G--` in Setup 17).
- **New pads: Voices, Filter 1, Filter 2** (1 voice and both filters off by default, as on the sampler). What every pad of a new project starts with. **Apply to all pads** sets them on the current project.
- **Sync compensation: Pull** (14 on H8 by default, 0 for off). A Pull (Setup 42) on one spare pad makes the sampler delay all its other sounds by that amount, about 0.15 ms per unit, while its MIDI clock stays on the grid. Gear that follows the sampler's clock trails it slightly; the Pull lines the sampler up with it. 14 (about 2.1 ms) was measured with a Cirklon driving an Akai S612. Leave the Pull pad empty: a sound there plays ahead of the others, and the tool asks before saving one.

## Voices and filters

Each pad has its own **Voices** (1–6, Setup 17) and **Filter 1** and **Filter 2** modes (Off, LP, HP or BP; Setups 31 and 32), set in the selected-pad panel. A pad with a filter on or more than one voice shows it on its tile, for example `LP×3`.

- **Voices**: how many hits of the same sound can overlap. At 1 a pad cuts off its own previous hit, as on an SP-1200. The sampler plays 16 voices in all, so raise this only where a sound needs to ring on.
- **Filter 1** is the filter the Ext mode cutoff sliders (per-sound and Global Cutoff) act on. With it off, those sliders do nothing for that pad. Cutoff, resonance and the envelope stay at their defaults for you to set on the sampler.

## Arranging

- Drag a pad onto another to swap them, or hold Alt to copy.
- Drag a bank letter onto another bank to swap whole banks, or hold Alt to copy.
- Sounds keep their output, voices and filter modes when moved. New audio dropped on a pad takes that pad's settings.
- **Undo** (Ctrl+Z) takes back the last change.

Keys: arrows select a pad, 1–8 set its output, Space plays, Delete clears, Enter renames.

## Notes

- This is an unofficial tool, not affiliated with or endorsed by MKSREC Electronics Limited.
- The `.mks`, `.sp12` and `.hfe` formats were worked out from example files rather than published specifications. Keep backups of anything important.

## Licence

GPL-3.0. See `LICENSE`.
