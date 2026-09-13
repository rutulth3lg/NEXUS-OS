# NEXUS OS

a single-file browser OS. dark theme, everything works, no build tools. open `index.html` and go.

inspired by arkham games + iron man HUD. built to actually be usable, not just a demo.

---

## what's in it

| module | what it does |
|--------|-------------|
| **Oracle AI** | groq API — llama-3.3-70b, ~145 tok/s. voice in + TTS out |
| **Music** | youtube iframe API. real playback, progress bar, shuffle/repeat |
| **Code Editor** | multi-file, line numbers, syntax highlighting, terminal, run button |
| **System Monitor** | live CPU/RAM sparklines, network stats, audio waveform |
| **Notes** | persistent (localStorage), formatting toolbar, word count |
| **Intel Feed** | weather (open-meteo API, real data), event log |
| **Lock Screen** | PIN pad with auto-lock timer |
| **Radar** | animated tactical radar with bat symbol. because why not |
| **Voice** | web speech API — speak commands, oracle replies out loud |

## setup

```bash
git clone https://github.com/rutulth3lg/NEXUS-OS.git
cd NEXUS-OS
open index.html
```

that's it. voice input needs HTTPS or localhost in chrome, so for full features:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

### groq key (for oracle AI)

1. free key at [console.groq.com](https://console.groq.com)
2. open NEXUS → Settings (key `9`)
3. paste key → **SAVE ALL SETTINGS**

or edit directly:
```js
const CFG = {
  groqKey: 'gsk_YOUR_KEY',
  city: 'Your City',
  owner: 'Your Name',
  pin: '1234',
};
```

## tech

single HTML file · groq API · youtube iframe API · web speech API · open-meteo API · localStorage
