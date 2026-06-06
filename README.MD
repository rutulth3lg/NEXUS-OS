# NEXUS OS v4.0 — Oracle Intelligence Platform

> *A fully functional dark OS-style browser interface. Batman aesthetics. Stark intelligence. Built for deep work.*

![NEXUS OS](https://img.shields.io/badge/NEXUS-v4.0-00c8ff?style=flat-square&labelColor=00050a)
![Oracle AI](https://img.shields.io/badge/Oracle-Groq%20LLaMA--3.3--70B-00ffcc?style=flat-square&labelColor=00050a)
![License](https://img.shields.io/badge/license-MIT-4488ff?style=flat-square&labelColor=00050a)

---

## What is this

A single-file browser OS interface — no build tools, no dependencies, no backend. Open `index.html` and it runs. Every feature actually works.

Inspired by the Arkham games, Iron Man's HUD, and Oracle from Batman Beyond. Built to be genuinely useful as a productivity environment, not just a demo.

---

## Features

| Module | What it does |
|--------|-------------|
| **Oracle AI** | Real Groq API — LLaMA-3.3-70B. ~145 tok/s. Voice input + TTS output. |
| **Music Engine** | YouTube IFrame API. Real playback, progress bar, volume, shuffle/repeat. Playlist of 12 tracks. |
| **Code Editor** | Multi-file IDE with line numbers, syntax highlighting via color, terminal, Run button. |
| **System Monitor** | Live CPU/RAM sparklines, network stats, threat radar, audio waveform. |
| **Secure Notes** | Persistent (localStorage), formatting toolbar, word count, Oracle integration. |
| **Intelligence Feed** | Threat matrix, weather station (Open-Meteo API, real data), event log. |
| **Workspace Launchers** | One-click launchers: Dev, Research, Trading, Focus, Writing, Music session. |
| **Lock Screen** | PIN pad + fingerprint sim. Auto-lock timer. |
| **Batman Radar** | Animated tactical radar with proper bat symbol at center. Glowing, breathing, rotating sweep. |
| **Voice** | Web Speech API — speak commands, Oracle replies in voice. |

---

## Setup

### Option 1 — Just open it
```
git clone https://github.com/YOURUSERNAME/nexus-os.git
cd nexus-os
open index.html
```
That's it. No npm, no build, no server needed for most features.

> Note: Voice input requires HTTPS or localhost in Chrome. For full functionality, serve locally.

### Option 2 — Local server (recommended for voice)
```bash
# Python
python3 -m http.server 8080

# Node
npx serve .

# Then open: http://localhost:8080
```

---

## Configuration

### Groq API Key (Oracle AI)
1. Get a free key at [console.groq.com](https://console.groq.com)
2. Open NEXUS → Settings (key `9` or sidebar)
3. Paste under **Groq API Key**
4. Hit **SAVE ALL SETTINGS**

Free tier: 14,400 req/day · 6,000 tokens/min — more than enough.

Or edit directly in `index.html`:
```js
const CFG = {
  groqKey: 'gsk_YOUR_KEY_HERE',
  city: 'Your City',
  lat: 0.0,
  lon: 0.0,
  owner: 'Your Name',
  pin: '1234',
};
```

### Weather
Uses [Open-Meteo](https://open-meteo.com/) — completely free, no key needed. Set your latitude/longitude in Settings.

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `1` – `9` | Switch views (Dash, Oracle, Code, Sys, Intel, Media, Workspace, Notes, Settings) |
| `Space` | Play / Pause music |
| `← →` | Previous / Next track |
| `V` | Toggle voice input |
| `L` | Lock OS |
| `Ctrl+S` | Save file / note |
| `Ctrl+F` | Fullscreen |
| `?` | Show shortcuts overlay |
| `Alt+D/R/T/F/W/M` | Workspace launchers |

---

## Architecture

Single file. No frameworks. No build step.

```
index.html
├── CSS (~1000 lines)  — variables, components, animations
├── HTML (~600 lines)  — views, panels, lock screen, boot
└── JS (~2400 lines)   — state machine, all features
    ├── Lock / Boot / Shell init
    ├── Metrics engine (CPU/RAM sparklines)
    ├── Batman radar (Canvas 2D)
    ├── Oracle AI (Groq API)
    ├── Voice (Web Speech API)
    ├── YouTube Music Engine
    ├── Code Editor + Terminal
    ├── Notes (localStorage)
    ├── Weather (Open-Meteo)
    └── Settings persistence
```

---

## Browser Support

| Browser | Status |
|---------|--------|
| Chrome / Edge | ✅ Full support |
| Firefox | ✅ Works (voice limited) |
| Safari | ⚠️ Voice may need permission |
| Mobile | ⚠️ Functional, not optimized |

---

## Customization

### Add tracks to the playlist
```js
const PLAYLIST = [
  { title:'Track Name', artist:'Artist', ytId:'YOUTUBE_VIDEO_ID', dur:240 },
  // dur = duration in seconds
];
```

### Change the PIN
Settings → PIN Code, or directly in `CFG.pin`.

### Change the owner name
Settings → Owner Callsign. Shows up in Oracle's greeting and boot sequence.

---

## Default PIN
`1234` — change it in Settings immediately.

---

## License

MIT — use it, fork it, build on it. Credit appreciated but not required.

---

*"The night is darkest just before the dawn."*