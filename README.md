# Relay Player for Samsung Tizen TV

Local player for **Enigma2 / streamrelay** HTTP MPEG-TS links.

Includes the full **SkyDe** channel list (34 channels with names & groups).

Repo: https://github.com/breakingbee/RelayplayerTIZEN

---

## Simple install steps (MU7000 / Tizen)

### 1. Turn on Developer Mode on the TV
1. Go to **Settings → Support → About This TV**
2. Click the **Samsung logo** (or “Smart Hub” text) **many times** until a Developer Mode popup appears
3. Switch **Developer Mode = On**
4. Enter the **IP address of your PC** (the one you’ll use for install)
5. TV will restart

### 2. Easiest way – Apps2Samsung (Windows)
1. Download **Apps2Samsung** from https://apps2samsung.com
2. Install and open it
3. Download this project as ZIP from GitHub  
   → green **Code** button → **Download ZIP** → unzip
4. In Apps2Samsung point to the unzipped folder (the one that contains `config.xml` + `index.html`)
5. Make sure TV and PC are on the **same Wi-Fi / LAN**
6. Click **Install** / **Deploy**
7. On the TV open the app **Relay Player** from Smart Hub / Apps

### 3. Alternative – Tizen Studio
1. Install Tizen Studio + TV Extension
2. Import the project folder
3. Create a certificate (Tools → Certificate Manager)
4. Right-click project → **Build Signed Package** → creates a `.wgt`
5. Connect to TV (`sdb connect TV_IP`) and install the `.wgt`

---

## How to use

| Remote key | Action |
|------------|--------|
| **← → ↑ ↓** | Move between channels |
| **OK** | Play selected channel |
| **Red** | Previous group (All / Sport / Cinema …) |
| **Green** | Next group |
| **Back** | Stop playback → back to list |
| **OK** (while playing) | Pause / Resume |
| **Red** (while playing) | Switch **audio** track |
| **Green** (while playing) | Switch **subtitles** |

You can still paste any custom `http://192.168.1.11:17999/...` link at the bottom.

---

## Channels included (from SkyDe.m3u)

**Sport** – DAZN 1, DAZN 2, Sky Sport 1, Mix, F1, Top Event, Austria 1, Premier League, Tennis, Golf, News, Austria 5, Bundesliga, Motorvision+

**Cinema** – Feelgood, Premiere, Action, Warner TV Film, Blockbuster, Classics, Sci-Fi

**Entertainment** – Sky One, Crime, 13th Street, Atlantic, Krimi, Showcase, Warner TV Comedy

**Documentary** – Sky Nature, NatGeo, NatGeo Wild, Sky Documentaries

**Music** – Jukebox  ·  **Kids** – Cartoon Network

---

## Requirements

- Samsung Tizen TV (2016+ / Tizen 3.0+) – tested for MU7000
- Your Enigma2 / streamrelay box reachable at `192.168.1.11:17999`
- TV and the relay box on the same local network
