# Relay Player for Samsung Tizen TV

Local player for Enigma2 / streamrelay HTTP MPEG-TS links (port 17999 style).

Designed for Samsung MU7000 and other Tizen 3.0+ TVs.

## Features

- Paste any `http://IP:17999/...` streamrelay link and play
- Recent links history (saved locally)
- **Audio track switching** (cycle with remote)
- **Subtitle track switching** (cycle with remote)
- Full remote support (D-pad, OK, Back, Play/Pause)
- Hardware-accelerated via Samsung AVPlay API

## How to install

### Option A – Apps2Samsung (easiest)
1. Download [Apps2Samsung](https://apps2samsung.com)
2. Enable Developer Mode on your TV (Settings → Support → About This TV → click Samsung logo several times)
3. Point Apps2Samsung at this folder (or the generated `.wgt`)
4. Install on the TV

### Option B – Tizen Studio
1. Import this project
2. Create a certificate
3. Package as `.wgt`
4. Install via Device Manager

## Remote controls while playing

| Key | Action |
|-----|--------|
| OK / Enter | Play / Pause |
| Back / Return | Stop and return to list |
| Red (or ColorA) | Cycle **Audio** track |
| Green (or ColorB) | Cycle **Subtitle** track |
| Up / Down | Navigate recent list (when in UI) |

## Files

- `index.html` – main app
- `config.xml` – Tizen widget config
- `icon.png` – app icon (optional)

## Notes

These streamrelay links are raw MPEG-TS over HTTP. TiviMate on Android plays them fine because of ExoPlayer. Samsung’s browser `<video>` usually fails. **AVPlay** is the correct native engine for this on Tizen.
