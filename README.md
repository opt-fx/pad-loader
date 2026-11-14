# MKSREC 1 Pad Loader

A browser tool for the MKSREC 1 sampler. It loads samples onto the sampler's 64 pads and saves a `.mks` project ready to copy to the card. The project matches a brand-new one from the sampler apart from the sounds and their outputs, so tuning, loops, envelopes and everything else stay at the defaults for you to set on the hardware. The whole app is one HTML file and runs in the browser with no install. Made by OPT.

**Use it now: https://opt-fx.github.io/mksrec1-pad-loader/**

**Status: first release.** Projects saved by the tool have loaded correctly on one MKSREC 1. Nothing is uploaded anywhere: your sounds stay on your computer.

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

Rossum SP-1200 `.sp12` projects can be imported with their sounds, names and outputs. Each sound keeps the SP-1200's 12-bit data with nothing added.

- **Import SP-1200…** puts a kit into the first banks where it overwrites nothing, so several kits can share one project.
- **Drop a `.sp12` file on a pad** to start the kit at that pad's bank.
- Pads that still carry an SP-1200 default name such as `A1` are named after the kit, for example `m808A1`.

## Outputs

Each pad goes to one of the sampler's eight outputs: 1–2 have the dynamic filters, 3–6 the static low-pass filters and 7–8 are clean. Set the selected pad's output with the 1–8 buttons or number keys, or drag a pad onto an output in the outputs panel. Hover over an output to see its pads. **Pad n → output n** and **Defaults** set every pad at once.

The output is set as Setup 17 sets it; choke groups are left off.

## Arranging

- Drag a pad onto another to swap them, or hold Alt to copy.
- Drag a bank letter onto another bank to swap whole banks, or hold Alt to copy.
- Sounds keep their outputs when moved. New audio dropped on a pad takes that pad's output.
- **Undo** (Ctrl+Z) takes back the last change.

Keys: arrows select a pad, 1–8 set its output, Space plays, Delete clears, Enter renames.

## Notes

- This is an unofficial tool, not affiliated with or endorsed by MKSREC Electronics Limited.
- The `.mks` and `.sp12` formats were worked out from example files rather than published specifications. Keep backups of anything important.

## Licence

GPL-3.0. See `LICENSE`.
