# Seilnetz V2.1: The Sonic Web

A sound-reactive 3D visualization that transforms MIDI input from a physical rope net installation into immersive audio and visuals.

## Quick Start

1. **Open** `index.html` in Google Chrome
2. **Click** the overlay to enable audio
3. **Play** using keys `1-6` or connect a MIDI device

---

## 🎹 Connecting MIDI Hardware

The webapp uses the **Web MIDI API** which reads devices already paired at the OS level.

### macOS Setup

1. Open **Audio MIDI Setup** (in `/Applications/Utilities/`)
2. Menu → **Window** → **Show MIDI Studio**
3. Click the **Bluetooth** icon (🔵) in the toolbar
4. Turn on your ESP32/MIDI controller
5. Click **Connect** when it appears
6. Open `index.html` in Chrome → Device auto-detected

### Windows Setup

Windows doesn't natively support Bluetooth MIDI. Options:

| Method                   | Description                                                                                                                                                                               |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **USB MIDI**             | Plug in directly. Works immediately.                                                                                                                                                      |
| **loopMIDI + MIDIberry** | Free. Creates virtual MIDI ports for BLE. [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html) + [MIDIberry](https://apps.microsoft.com/store/detail/midiberry/9N39720H2M05) |
| **BOME Bluetooth MIDI**  | Paid ($29). Most reliable BLE MIDI bridge.                                                                                                                                                |

Once your device is visible to Windows, Chrome will see it via Web MIDI API.

### Testing Without Hardware

- Press keys **1-6** on your keyboard
- Click **Start Auto-Play** for random demo stream

---

## 🔊 Sound Presets

| Preset                   | Character                             | Use Case                  |
| ------------------------ | ------------------------------------- | ------------------------- |
| **CMaj9 – Safe**         | Warm, consonant, forgiving            | Default. Always pleasant. |
| **Pentatonic – Bright**  | Clear, crystalline, higher register   | More "present" sound      |
| **Eno Drones – Ambient** | Slow swells, long release, washy      | Meditative, ambient       |
| **A♭m7 – Melancholic**   | Minor 7th jazz voicing, introspective | Emotional, contemplative  |
| **C♭maj7 – Ethereal**    | Enharmonic Bmaj7, slightly dissonant  | Dreamy, otherworldly      |
| **Chaos + Screech**      | 5 nice notes + 1 EAR-PIERCING         | Demonstrates range, alarm |

---

## 🎮 Controls

| Input          | Action              |
| -------------- | ------------------- |
| **Keys 1-6**   | Trigger sensors 0-5 |
| **Left-drag**  | Rotate camera       |
| **Scroll**     | Zoom in/out         |
| **Right-drag** | Pan camera          |

---

## 📁 Files

```
seilnetz/
├── index.html       # Main app (Tone.js + Three.js)
├── midi-debug.html  # MIDI diagnostics console
├── README.md        # This file
├── DESIGN_DOC.md    # Design document
└── *.png            # Reference photos
```

---

## 🔧 For Collaborators

### Sharing with Others

1. Send them `index.html` (or share the GitHub repo)
2. They open it in Chrome
3. If using MIDI hardware: follow OS-specific setup above
4. If testing: use keyboard keys 1-6 or Auto-Play

### ESP32 MIDI Protocol (Paracord-Drums)

The webapp is configured for the **Paracord-Drums** hardware which uses:
- **MIDI Channels 1-6** → Map to Sensors 0-5 (channel - 1 = sensor index)
- **Note Number:** Fixed at 60 (middle C) - not used for mapping
- **Velocity:** 1-127 (affects volume and visual intensity)

**Example:** Channel 2, Note 60, Velocity 80 → Triggers Sensor 1 at 80% intensity

---

## 🔧 Hardware Integration Notes

### Observed Behavior (Dec 2025 Testing)
- **Velocity floor:** ~50 (set by ESP32 firmware's `map()` function)
- **Multiple triggers per hit:** Piezo sensors "ring" after impact, causing ~20 events per flick
- **Ghost channel (Ch 3):** Floating analog pin or crosstalk

### What to Fix Where

| Issue             | Fix Location   | Solution                                           |
| ----------------- | -------------- | -------------------------------------------------- |
| Velocity range    | ESP32 firmware | Adjust `map(value, THRESHOLD, 4095, MIN_VEL, 127)` |
| Multiple triggers | ESP32 firmware | Increase `DEBOUNCE_MS` to 300-500ms                |
| Ghost sensors     | ESP32 wiring   | Add pull-down resistors to unused pins             |
| Channel mapping   | Web app ✅      | Already configured: `sensor = channel - 1`         |

### Web App Debouncing
The web app includes a **150ms debounce** as a safety net, but the ESP32 firmware should handle this primarily.

---

## 🛠️ Debug Tools

Open `http://localhost:8765/midi-debug.html` for comprehensive MIDI diagnostics:

- **System Status:** Web MIDI API, permissions, device count
- **Device List:** All connected MIDI inputs with metadata
- **Live Messages:** Real-time log with Note On/Off, CC, channel info
- **Statistics:** Total messages, Note On count, last active channel
- **Setup Guide:** Platform-specific pairing instructions

---

## Architecture

```
┌─────────────────────────────────────────────────┐
│              INPUT SOURCES                      │
│   MIDI (ESP32)  │  Keyboard (1-6)  │  AutoPlay  │
└────────┬────────┴────────┬─────────┴────┬───────┘
         └─────────────────┼──────────────┘
                           ▼
                    ┌─────────────┐
                    │  Event Bus  │
                    └──────┬──────┘
           ┌───────────────┼───────────────┐
           ▼               ▼               ▼
    ┌────────────┐  ┌────────────┐  ┌────────────┐
    │   Audio    │  │    Viz     │  │    Log     │
    │  (Tone.js) │  │ (Three.js) │  │   (DOM)    │
    └────────────┘  └────────────┘  └────────────┘
```

---

## License

Part of the Design & Computation program project work.
