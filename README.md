# Normalize to LUFS

An Ableton Live extension that measures and normalizes audio clips to a target integrated loudness (LUFS) per ITU-R BS.1770-4 / EBU R128.

## Installation

1. Download the latest `.ablx` file from [Releases](https://github.com/chymeramusic/normalize-to-lufs/releases) or from this repository.
2. Double-click the `.ablx` file, or drag it into Ableton Live.
3. The extension appears in the right-click context menu on audio clips.

## Usage

Right-click an audio clip (or select multiple clips / a time range) and choose **Normalize to LUFS: Normalize to LUFS...**

A dialog appears with the following options:

### Target LUFS

Enter the desired integrated loudness. The extension remembers the last value you used. Common targets:

| Platform | Target |
|----------|--------|
| Spotify  | -14 LUFS |
| YouTube  | -13 LUFS |
| Apple Music | -16 LUFS |

### Action

- **Normalize clips in place** - Replaces each selected clip with a loudness-normalized version. Supports undo (Cmd/Ctrl+Z). Always outputs WAV 32-bit float at the source sample rate.
- **Export each clip (normalised)** - Exports each selected clip as a separate normalized audio file to the project's Samples/Processed folder. Original clips are left untouched.
- **Export each track (bounce & normalise)** - Requires an Arrangement time-range selection. Bounces each selected audio track within the time range and exports as a normalized file to Samples/Processed.
- **Export from main (bounce & normalise)** - Requires an Arrangement time-range selection. Renders all audio tracks in the project for the selected time range, mixes them down to stereo, normalizes, and exports a single file to Samples/Processed.

### Export settings

These options apply to all export modes (greyed out for normalize-in-place):

- **Format** - WAV or AIFF
- **Sample rate** - Original (keep source rate), 44,100 Hz, 48,000 Hz, 88,200 Hz, or 96,000 Hz
- **Bit depth** - 16-bit, 24-bit (default), or 32-bit float

### Apply limiter

Off by default. When enabled, a brickwall sample-peak limiter at -1 dBFS prevents any sample from clipping. When limiting is required, the final loudness may fall slightly below the target.

## Selection modes

| How you select | What gets processed |
|---|---|
| Right-click a single audio clip | That clip |
| Select clip slots in Session View, right-click | All selected clips |
| Drag a time-range selection in Arrangement View, right-click | All audio clips / tracks in the range |

## Requirements

- Ableton Live with Extensions support (API version 0.0.5 or later)

## Author

Brendan - [chymeramusic](https://github.com/chymeramusic)
