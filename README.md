# Relay Player for Samsung Tizen TV

Local player for **Enigma2 / streamrelay** HTTP MPEG-TS links (port `17999` style).

Built for Samsung **MU7000** and other Tizen 3.0+ TVs.

Repo: [breakingbee/RelayplayerTIZEN](https://github.com/breakingbee/RelayplayerTIZEN)

## Features

- Paste any `http://IP:17999/...` streamrelay link and play
- Recent links history (saved in localStorage)
- **Audio track switching** (cycle with remote)
- **Subtitle track switching** (cycle with remote)
- Full remote support (D-pad, OK, Back, Play/Pause, color keys)
- Hardware-accelerated via Samsung **AVPlay** API (required for raw TS)

## How to install

### Option A – Apps2Samsung (easiest)
1. Download [Apps2Samsung](https://apps2samsung.com)
2. Enable **Developer Mode** on the TV  
   `Settings → Support → About This TV` → click the Samsung logo several times → set IP of your PC
3. Point Apps2Samsung at this project folder (or the generated `.wgt`)
4. Install on the TV

### Option B – Tizen Studio
1. Import this project
2. Create a certificate (or use an existing one)
3. Right-click → **Build Signed Package** → produces a `.wgt`
4. Install via Device Manager / sdb

```bash
sdb connect <TV_IP>
sdb install RelayPlayer.wgt
```

## Remote controls

### While playing

| Key | Action |
|-----|--------|
| **OK / Enter** | Play / Pause |
| **Back / Return** | Stop → return to link list |
| **Red** (ColorA) | Cycle **Audio** track |
| **Green** (ColorB) | Cycle **Subtitle** track |
| **Yellow** | Refresh track list |
| Media Stop | Stop |

### In the UI

| Key | Action |
|-----|--------|
| Up / Down | Navigate recent list |
| OK | Play selected / current URL |

## Files

| File | Purpose |
|------|---------|
| `index.html` | Full app (UI + AVPlay + track switching) |
| `config.xml` | Tizen widget manifest + privileges |
| `icon.png` | App icon (optional – add your own 512×512) |

## Why AVPlay?

These streamrelay links are raw **MPEG-TS over HTTP**.  
TiviMate on Android plays them fine (ExoPlayer).  
Samsung’s browser `<video>` usually fails on this format.  
**AVPlay** is the native hardware player that can handle it on Tizen.

## Notes / limitations

- Multiple audio PIDs are common on satellite/cable streams → Red button cycles them.
- Subtitles (DVB/teletext) depend on the stream; many streamrelay feeds have none.
- Track list is refreshed a couple of times after play starts (live TS can be slow to report tracks).
- Tested against Tizen 3.0+ (MU7000 era). Newer TVs should work the same.

## Example link

```
http://192.168.1.11:17999/11758:H:27500:008D:0002:0085:0
```
