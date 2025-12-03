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

| Preset                   | Character                           | Use Case                  |
| ------------------------ | ----------------------------------- | ------------------------- |
| **CMaj9 – Safe**         | Warm, consonant, forgiving          | Default. Always pleasant. |
| **Pentatonic – Bright**  | Clear, crystalline, higher register | More "present" sound      |
| **Eno Drones – Ambient** | Slow swells, long release, washy    | Meditative, ambient       |
| **Chaos + Screech**      | 5 nice notes + 1 EAR-PIERCING       | Demonstrates range, alarm |

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
├── index.html      # Complete app (single file)
├── README.md       # This file
├── DESIGN_DOC.md   # Original design document
└── *.png           # Reference photos of physical net
```

---

## 🔧 For Collaborators

### Sharing with Others

1. Send them `index.html` (or share the GitHub repo)
2. They open it in Chrome
3. If using MIDI hardware: follow OS-specific setup above
4. If testing: use keyboard keys 1-6 or Auto-Play

### ESP32 MIDI Protocol

The webapp expects:
- **MIDI Channel:** Any
- **Note Numbers:** `0-5` (maps directly to sensors) OR higher notes (modulo 6)
- **Velocity:** `1-127` (affects volume and visual intensity)

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
