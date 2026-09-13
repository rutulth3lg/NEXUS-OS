# NEXUS OS

A single-file browser OS. Dark theme, everything works, no build tools. Open `index.html` and go.

Inspired by Arkham games + Iron Man HUD. Built to actually be usable, not just a demo.

---

## What's In It

| Module | What it does |
|--------|-------------|
| **Oracle AI** | Groq API — LLaMA-3.3-70B, ~145 tok/s. Voice in + TTS out |
| **Music** | YouTube IFrame API. Real playback, progress bar, shuffle/repeat |
| **Code Editor** | Multi-file, line numbers, syntax highlighting, terminal, run button |
| **System Monitor** | Live CPU/RAM sparklines, network stats, audio waveform |
| **Notes** | Persistent (localStorage), formatting toolbar, word count |
| **Intel Feed** | Weather (Open-Meteo API, real data), event log |
| **Lock Screen** | PIN pad with auto-lock timer |
| **Radar** | Animated tactical radar with bat symbol |
| **Voice** | Web Speech API — speak commands, Oracle replies out loud |

## Setup

```bash
git clone https://github.com/rutulth3lg/NEXUS-OS.git
cd NEXUS-OS
open index.html
```

That's it. Voice input needs HTTPS or localhost in Chrome, so for full features:

```bash
python3 -m http.server 8080
# Open http://localhost:8080
```

### Groq Key (for Oracle AI)

1. Free key at [console.groq.com](https://console.groq.com)
2. Open NEXUS → Settings (key `9`)
3. Paste key → **SAVE ALL SETTINGS**

Or edit directly:
```js
const CFG = {
  groqKey: 'gsk_YOUR_KEY',
  city: 'Your City',
  owner: 'Your Name',
  pin: '1234',
};
```

## Tech

Single HTML file · Groq API · YouTube IFrame API · Web Speech API · Open-Meteo API · localStorage
