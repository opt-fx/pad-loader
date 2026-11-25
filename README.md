# Pad Loader

**For the MKSREC 1 sampler.** An unofficial community tool, not affiliated with or endorsed by MKSREC Electronics Limited.

Pad Loader is a browser tool for the MKSREC 1. It does three things:

- **Loads samples onto the sampler's 64 pads** and saves a fresh `.mks` project ready to copy to the card. Apart from the sounds, their outputs, voices and filter modes, and a few project settings, the project matches a brand-new one from the sampler, so tuning, loops, envelopes and the rest stay at the defaults for you to set on the hardware.
- **Splits OP-1 drum kits onto pads**: a Teenage Engineering OP-1 drum `.aif` becomes one sound per slice.
- **Imports SP-1200 kits onto pads**, from a Rossum `.sp12` project or an original SP-1200 floppy image (`.hfe`), with their names, outputs, tuning and decay.
- **Converts Rossum `.sp12` projects to `.hfe` floppy images**, so the sampler can import a whole kit, sequences and songs included.
- **Has a reference card** for the sampler's Setup codes, Special functions, Disk keys and key shortcuts, searchable and printable on one page.

The whole app is one HTML file and runs in the browser with no install. Nothing is uploaded anywhere: your sounds stay on your computer. Made by OPT.

**Use it now: https://opt-fx.com/pad-loader/**

**Status: version 1.2.** Saved projects, SP-1200 imports and converted floppies have all loaded correctly on an MKSREC 1. SP-1200 imports match the sampler's own conversion of the same floppies sample for sample.

## Quick start

1. Open the app's page, or download `index.html` and open it from disk, in a current version of Chrome, Edge, Firefox or Safari.
2. Drop audio files onto a pad. Several files fill the pads that follow, in name order.
3. Set each pad's output if you need to (see Outputs).
4. Type a file name and press **Save .mks**.
5. Copy the file into the card's `/Songs` folder and load it on the sampler in Disk mode.


### Install it as an app

Pad Loader can be installed so it opens from the Dock or Start menu in its own window and works offline. In Chrome or Edge, click **Install app** at the top of the page, or the install icon at the right of the address bar. In Safari on a Mac (macOS Sonoma or later), choose File → Add to Dock. Firefox can't install web apps. It opens instantly from the copy on your computer and checks for an update in the background, so a new version appears the next time you open it, and the Activity panel notes it once.

To send someone straight to the install offer, link to [opt-fx.com/pad-loader/#install](https://opt-fx.com/pad-loader/#install).

## Adding sounds to an existing project

**Open .mks…** (or drop a `.mks` file on the page) opens a project saved by the sampler, so you can add sounds to one you've already worked on. Put the new sounds on empty pads and save. Everything else is written back exactly as the sampler saved it: segments, songs, mixes, and each existing pad's sound and settings, such as tuning, loops and envelopes.

- The project keeps its own tempo and trigger delays (Setup 42), so the Tempo and Sync compensation Pull settings are not applied to it.
- The new-pad settings apply only to New projects. Sounds added to an opened project take the settings that pad already has on the sampler, such as its output and choke group, and you can change them as usual.
- Patterns play pads by position. Moving or swapping a sound in an opened project changes what the patterns play, so add new sounds to free pads rather than rearranging the old ones.
- Save under a new name, or keep a backup, until you've checked the result on the sampler.

## Loading sounds

- **Audio files.** WAV, AIFF, MP3, FLAC and OGG. The tool reads AIFF itself (8- to 32-bit, and uncompressed or floating-point AIFF-C), because most browsers can't; compressed AIFF-C needs exporting as WAV or plain AIFF first. The other formats use the browser's own decoder. Audio is converted the way the sampler converts WAVs: left channel only, resampled to 26,040 Hz. Each sound is named from the first six characters of its file name; click the name to change it.
- **Conversion.** The sampler's import modes are available: clean, 12b, 8b, 8b ul, 6b and 6b ul. Set the mode for new sounds in the toolbar, or change it per pad. The original audio is kept, so you can switch modes and listen to the difference. 12b d and gleam are not reproduced; load the WAV on the sampler for those.
- **OP-1 drum kits.** An OP-1 drum kit is one `.aif` with the slice points for its 24 keys stored inside. Drop it on a pad, or choose it with Load audio, and each distinct slice goes on its own pad from that pad onwards, in key order. Keys the OP-1 filled with a repeat of another slice are skipped, so a 12-sound kit takes 12 pads. Silence at the end of each slice is trimmed, and sounds are named from the first four characters of the file name plus the slice number, such as `gadg01`. The kit's pitch, volume and effect settings are not carried over. OP-1 synth sampler files hold a single sound and load as one.
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

Each pad goes to one of the sampler's eight outputs: 1–2 have the dynamic filters, 3–6 the static low-pass filters and 7–8 are clean. Set the selected pad's output with the 1–8 buttons or number keys, or drag a pad onto an output in the outputs panel. To set several pads at once, select them first (see Selecting several pads). Hover over an output to see its pads. **Pad n → output n** and **Defaults** set every pad at once.

The output is set as Setup 17 sets it.

## Project settings

Written into every project you save, and remembered in the browser:

- **New pads: No choke groups, Voices, Filter 1, Filter 2** (no choke groups, 1 voice and both filters off by default). What every pad of a new project starts with. **Apply to all pads** sets them on the current project. With No choke groups unticked, pads start on the sampler's own default, which puts every odd pad in choke group 7 and every even pad in group 8, so any odd pad cuts off any other odd pad.
- **Tempo** (120 BPM by default). The tempo written into every song of a new project, 40–240 BPM in steps of 0.1. The sampler plays a loaded project at its song tempo, and a tempo set in Segment mode is only temporary, so set your usual tempo here. An opened project keeps its own.
- **Sync compensation: Pull** (14 on H8 by default, 0 for off). A Pull (Setup 42) on one spare pad makes the sampler delay all its other sounds by that amount, about 0.15 ms per unit, while its MIDI clock stays on the grid. Gear that follows the sampler's clock trails it slightly; the Pull lines the sampler up with it. 14 (about 2.1 ms) was measured with a Cirklon driving an Akai S612. Leave the Pull pad empty: a sound there plays ahead of the others, and the tool asks before saving one.

## Choke groups, voices and filters

Each pad has its own **Choke group** (none or 1–8) and **Voices** (1–6), both from Setup 17, and **Filter 1** and **Filter 2** modes (Off, LP, HP or BP; Setups 31 and 32), set in the selected-pad panel. A pad with a choke group, a filter on or more than one voice shows it on its tile, for example `G1 LP ×3`.

- **Choke group**: a hit on any pad in a group stops the others in that group, such as open and closed hi-hats. Pads sent to the same output do not cut each other off on the MKSREC 1, unlike an SP-1200 channel, so for a sliced break put all its slices in one group. After loading several files at once, give one of them a group and press **Group n for all pads of this load** to put the whole load in it.
- **Voices**: how many hits of the same sound can overlap. At 1 a pad cuts off its own previous hit, but not other pads; that needs a choke group. The sampler plays 16 voices in all, so raise this only where a sound needs to ring on.
- **Filter 1** is the filter the Ext mode cutoff sliders (per-sound and Global Cutoff) act on. With it off, those sliders do nothing for that pad. Cutoff, resonance and the envelope stay at their defaults for you to set on the sampler.

## Selecting several pads

Shift-click a pad to select every pad from the last one you clicked, or Ctrl-click (⌘-click on a Mac) to add or remove single pads. The side panel then shows the first pad and how many more are selected, and its output, choke group, voices and filter buttons set all of them at once; a button is lit only when every selected pad shares that value. The number keys and **Clear** act on the whole selection too, and dragging one of the selected pads onto an output moves them all.

## Arranging

- Drag a pad onto another to swap them, or hold Alt to copy.
- Drag a bank letter onto another bank to swap whole banks, or hold Alt to copy.
- Sounds keep their output, voices and filter modes when moved. New audio dropped on a pad takes that pad's settings.
- **Undo** (Ctrl+Z) takes back the last change.

Keys: arrows select a pad, 1–8 set its output, Space plays, Delete clears, Enter renames.

## Reference

**Reference**, at the top of the side column, swaps the pad settings for a quick guide to the sampler: every Setup code, the Special functions (Setup 23), the Disk mode keys and the main key shortcuts. Type in the search box to find a code or a word, such as `choke` or `42`, or pick a section. **Print** gives the whole guide on one page. Clicking a pad goes back to the pad settings.

The guide was written from the MKSREC 1 manual for firmware 111026 (Setup 99 shows the firmware date). Later firmware may add or change functions; the manual has the full details.

## Notes

- Pad Loader is an unofficial community tool, not affiliated with or endorsed by MKSREC Electronics Limited. MKSREC is a registered trade mark of MKSREC Electronics Limited, used here only to say which sampler the tool works with.
- The `.mks`, `.sp12` and `.hfe` formats were worked out from example files rather than published specifications. Keep backups of anything important.

## Licence

GPL-3.0. See `LICENSE`.
