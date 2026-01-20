# 🕸️ Sonic Web (Nervensystem)

**A restorative, haptic-acoustic sanctuary — a walkable rope net and spatial harp that transforms touch into sound, creating a "spatial diversion" for mental resets.**

|                           |                                                    |
| ------------------------- | -------------------------------------------------- |
| **Course**                | Perspectives in Design — Robotic Renovation        |
| **Team**                  | Antonia, Lilian, Mate, Vincent                     |
| **Abschlusspräsentation** | ~3 weeks (D&C students/faculty, theoretical focus) |
| **Ausstellung**           | ~4 weeks (public, practical/guided)                |

## 🚨 Current Status & Priorities

| Priority | Task                                                    | Status        | Owner        |
| -------- | ------------------------------------------------------- | ------------- | ------------ |
| **P0**   | Fix sensor electronics (multiple piezos not triggering) | 🔴 Blocked     | TBD          |
| **P1**   | Complete harp/tent construction                         | 🟡 In Progress | Team         |
| **P1**   | Finalize soundscape approach                            | 🟡 Deciding    | Lilian       |
| **P2**   | Stakeholder outreach for materials                      | 📋 Planned     | Mate/Vincent |
| **P3**   | Guerilla action (playground/atrium install)             | ⏸️ Parked      | —            |

### 🎯 Open Decisions

1. **Soundscape Philosophy:** Triggered sounds (original) vs. continuous "Klangteppich" (calming drones triggered by first movement)?
2. **Harp Sound Character:** Monochord-inspired (meditative, [reference](https://youtu.be/c1aCNMIZ5lM)) vs. melodic plucking?
3. **Presentation Framing:** How to differentiate Abschlusspräsentation (theoretical/artsy) from Ausstellung (practical)?

## 🏛️ Concept & Design

### Functional Intent (Why)

The Sonic Web is designed as a **restorative escape** — a "chillout zone" facilitating mental resets from cognitive overload or loud environments.

| Intent                   | Description                                                                                              |
| ------------------------ | -------------------------------------------------------------------------------------------------------- |
| **Restorative Escape**   | A spatial diversion for high-stress environments (studios, ateliers, academic settings)                  |
| **Psychological Safety** | The "princess bed" effect — enclosure and protection foster relaxation                                   |
| **Co-Creation**          | During exhibition, audience transitions from observers to contributors by knitting open spots in the net |

### The Renovation Question

> *"What happens when we not only use technologies for renovation, but rather adapt and alter, when we manipulate and mess with them towards unknown outcome?"*

The project began in the Alter Lesesaal with a suspended rope net — a chill-out space where students sit, recline, and gather. It's comfortable but **mute**. We give it a **nervous system**: the ability to feel touch and respond with sound.

**Location flexibility:** While rooted in the "renovation" thesis, the installation can adapt to multiple contexts — the original studio, the university atrium, or outdoor settings.

**Inspiration:** Tomás Saraceno's "Space Nets" and spider web installations — tensile structures as instruments of connection.

### User Stories

| Perspective   | Story                                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Student**   | "I want subtle, pleasing sounds when I shift my weight, so I feel connected to the space without being overwhelmed." |
| **Performer** | "I want to hit or pull specific sections to trigger distinct sounds, allowing me to 'jam' with the structure."       |
| **Creator**   | "I want to map physical inputs to audio parameters so output feels organic and not repetitive."                      |

### Design Principles

| Principle                  | Implementation                                                                   |
| -------------------------- | -------------------------------------------------------------------------------- |
| **Prosthetic Thinking**    | Additive, not destructive. Sensors removable. Net remains functional seating.    |
| **Harmonic Constraints**   | Pentatonic scale + slow attack + long release = always pleasant                  |
| **Participation Spectrum** | Passive presence → subtle drones. Active play → melodic notes.                   |
| **Ma (間)**                | Sound emerges from silence and returns to it. The net should not be "always on." |

### ⚠️ Safety Note

The load-bearing rope knots must be verified by someone with rigging experience before people hang their full body weight. The "musical" sensing layer must **never interfere with structural integrity** — sensors are taped, not tied into load paths.

## 🔧 Physical Form & Materiality

### Current Construction

```
            ┌─────────────────────┐  ← Overhead Beam (suspended)
            │    ╲     │     ╱    │     with center string pulling
            │     ╲    │    ╱     │     the net upward
            │      ╲   │   ╱      │
            │       ╲  │  ╱       │
     ┌──────┼────────╲─┼─╱────────┼──────┐
     │Pillar│         ╲│╱         │Pillar│
     │      │   ┌──────┴──────┐   │      │
     │      │   │             │   │      │
     │      │   │  🕸️ WEB     │   │      │  ← 3D tent shape
     │      │   │  (main net) │   │      │
     │      │   │             │   │      │
     └──────┼───┴─────────────┴───┼──────┘
            │                     │
            │   🎸 HARP/TENT      │  ← ~30% coverage, attached
            │   (side net)        │     to frame + pillar
            └─────────────────────┘
                Round Steel Truss
```

| Component                | Description                                                                      |
| ------------------------ | -------------------------------------------------------------------------------- |
| **Frame**                | Round steel truss with overhead steel beam (carried by two upright pillars)      |
| **Web (main net)**       | Paracord, attached to circular frame, semi-random angular weaving, ~70% coverage |
| **Harp/Tent (side net)** | Paracord, attached to frame + pillar, ~30% coverage, tent-like appearance        |
| **3D Shape**             | Center string from overhead beam pulls web upward → tent-like volume (not flat)  |

**Design goals:**
- More comfortable and interesting seating (3D contours)
- Cozy atmosphere (harp enclosure creates "princess bed" effect)
- Different sonic affordances (harp = pluckable instrument, net = ambient body sensing)

### Materials & Rope Types

| Material             | Properties                                       | Status           |
| -------------------- | ------------------------------------------------ | ---------------- |
| **Paracord (nylon)** | Durable, good haptics, minimal stretch           | ✅ Current choice |
| **Static ropes**     | No stretch (used by treenet professionals)       | Alternative      |
| **Climbing ropes**   | Too much stretch, but core = multiple thin ropes | Research idea    |
| **Hemp**             | Natural haptics, sustainable                     | Untested         |
| **Conductive yarn**  | Could integrate sensing directly                 | Future R&D       |

**Note:** Climbing rope cores consist of multiple thinner ropes — potentially could replace paracord if deconstructed. Recycled climbing gear from gyms could be a sustainable material source.

### Net vs. Harp Comparison

| Aspect              | Net (Web)                        | Harp (Tent)            |
| ------------------- | -------------------------------- | ---------------------- |
| **Geometry**        | Horizontal, 3D contoured         | Vertical, curtain-like |
| **Interaction**     | Body weight, shifting, reclining | Plucking, strumming    |
| **Affordance**      | Ambient, gradual                 | Melodic, intentional   |
| **Sound character** | Drones, swells                   | Notes, arpeggios       |
| **Inspiration**     | Body sensing                     | Monochord instrument   |

## 🔌 Technical Architecture

### System Overview

```
┌─────────────────────────────────────────────────────────────┐
│  PHYSICAL    User → Rope/Harp → Vibration → Piezo → Voltage │
├─────────────────────────────────────────────────────────────┤
│  DIGITAL     ESP32: Threshold → Debounce → BLE MIDI         │
├─────────────────────────────────────────────────────────────┤
│  SOUND       Browser (Tone.js + Three.js) → Speakers        │
└─────────────────────────────────────────────────────────────┘
```

### Hardware

| Component        | Choice                     | Rationale                                              |
| ---------------- | -------------------------- | ------------------------------------------------------ |
| **Net Sensors**  | Piezo elements (×6+)       | Cheap, sensitive, robust. No structural changes.       |
| **Harp Sensors** | Piezo elements (TBD count) | Same tech, different mounting for vertical strings     |
| **MCU**          | ESP32 (WROOM) or Teensy    | Built-in BLE MIDI — no cables between net and computer |
| **Power**        | USB battery                | Hidden in truss                                        |

**Known issues (P0):**
- Velocity floor ~50 (firmware)
- Multiple triggers per hit (piezo ringing)
- Ghost Channel 3 (floating pin)
- **Sensor electronics need fixing** — multiple piezos not triggering correctly

### Software Stack

| Component            | Technology                           | Purpose                                      |
| -------------------- | ------------------------------------ | -------------------------------------------- |
| **Audio Engine**     | [Tone.js](https://tonejs.github.io/) | Web Audio synthesis, effects, scheduling     |
| **3D Visualization** | [Three.js](https://threejs.org/)     | Real-time visual feedback of sensor activity |
| **MIDI Input**       | Web MIDI API                         | BLE MIDI from ESP32 hardware                 |

**Why Web-Based:** Zero install, cross-platform, easy iteration, visual + audio unified.

**Files:** `index.html` (main app), `midi-debug.html` (hardware testing)

## 🎵 Sound Design

### Soundscape Philosophy (Open Decision)

Two approaches under consideration:

| Approach                 | Description                                           | Pros                                                | Cons                           |
| ------------------------ | ----------------------------------------------------- | --------------------------------------------------- | ------------------------------ |
| **Triggered (original)** | Each movement triggers a discrete sound               | Interactive, responsive                             | Calming sounds need continuity |
| **Klangteppich (new)**   | First movement triggers continuous ambient soundscape | Better for calming (white/brown noise, alpha waves) | Less interactive feel          |

**Potential hybrid:** Harp = triggered (monochord-like), Net = Klangteppich (ambient carpet activated by first contact).

### The "Guaranteed Pleasant" Strategy

1. **Pentatonic Scale** — Mathematically impossible to play dissonance
2. **Open Voicing** — Spread notes across spectrum (bass ↔ treble) to avoid mud
3. **Slow Attack (200-500ms)** — Sounds "swell" rather than "beep" — hides sensor jitter
4. **Long Release (3-5s)** — Notes linger like bells — fills silence without constant input
5. **Velocity → Brightness** — Map force to filter cutoff: gentle = muffled/warm, strong = bright/airy

### Sound Presets (Web App)

| Preset               | Character                 |
| -------------------- | ------------------------- |
| CMaj9 – Safe         | Warm, consonant (default) |
| Pentatonic – Bright  | Clear, crystalline        |
| Eno Drones – Ambient | Slow swells, washy        |
| A♭m7 – Melancholic   | Minor 7th, introspective  |

### Recommended Note Map (C Major 9)

| Sensor | Role    | MIDI | Note |
| ------ | ------- | ---- | ---- |
| 1      | Bass    | 36   | C2   |
| 2      | Fifth   | 43   | G2   |
| 3      | Tenor   | 52   | E3   |
| 4      | Alto    | 59   | B3   |
| 5      | Soprano | 62   | D4   |
| 6      | Air     | 67   | G4   |

## 📋 Stakeholder Outreach

**General ask:** Introduce project, explore collaboration, request materials or space if relevant.

### Material Sources (Prioritized)

| Category             | Contacts                                                           | Ask                                            |
| -------------------- | ------------------------------------------------------------------ | ---------------------------------------------- |
| **Kletterhallen**    | Magic Mountain, DAV Berlin, Southrock, TU Hochschulsport           | Decommissioned climbing ropes (30-40m lengths) |
| **Baumpflege**       | Baumdienstkönig, Baumpflege Kasper, Biber Baumdienst               | Static ropes for tree work                     |
| **Paracord Händler** | Paracord.eu, 123Paracord.de, Messer & Co                           | Material sponsorship or discount               |
| **Outdoor Retail**   | Aliens Outdoor ("Schnittreste" >20m), NewSeed ("Recyclingpartner") | Recycled/offcut materials                      |

### Sponsorship & Industry

| Category                     | Contacts                                                                                  | Angle                                 |
| ---------------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------- |
| **Outdoor Brands**           | Globetrotter (donation program), Decathlon (cooperations), Edelrid, Gibbon Slacklines     | Sustainability story, student project |
| **Playground Manufacturers** | Lappset (Sona), Berliner Seilfabrik (Frameworx), smb Seilspielgeräte, Richter Spielgeräte | Musical playground R&D partnership    |

### Owner Assignment

| Owner       | Focus |
| ----------- | ----- |
| **Mate**    | TBD   |
| **Vincent** | TBD   |

## 🖥️ Usage Guide

### Quick Start

1. **Open** `index.html` in Chrome
2. **Click** overlay to enable audio
3. **Play** with keys `1-6` or connect MIDI hardware

**Without hardware:** Press `1-6` on keyboard, or click "Start Auto-Play".

### MIDI Setup

**macOS:** Audio MIDI Setup → Window → Show MIDI Studio → Bluetooth icon → Connect ESP32

**Windows:** Native BLE MIDI not supported. Use USB MIDI, or loopMIDI + MIDIberry (free), or BOME ($29).

### Controls

| Input     | Action              |
| --------- | ------------------- |
| Keys 1-6  | Trigger sensors 0-5 |
| Left-drag | Rotate camera       |
| Scroll    | Zoom                |

## 📅 Timeline & Phases

| Phase                        | Focus                                                         | Status               |
| ---------------------------- | ------------------------------------------------------------- | -------------------- |
| **1. Research**              | Saraceno study, net analysis, sound exploration               | ✅ Complete           |
| **2. Prototype**             | Single sensor, BLE MIDI test, sound palette, net construction | ✅ Complete (Midterm) |
| **3. Iteration**             | Harp extension, 3D tent shape, sound refinement               | 🔄 In Progress        |
| **4. Abschlusspräsentation** | Conceptual/theoretical framing (D&C internal)                 | 📅 ~3 weeks           |
| **5. Ausstellung**           | Full installation, public exhibition, guided experience       | 📅 ~4 weeks           |

## 🔮 Future Directions (Parked)

> **Current Focus:** Execute net + harp for Feb 2026 final. Everything below is parked.

| Direction              | Description                                               | Status  |
| ---------------------- | --------------------------------------------------------- | ------- |
| 🧠 **Biofeedback**      | Mood-sensing, heart rate, GSR for adaptive soundscape     | Parked  |
| 👼 **Angel Walk**       | Recorded affirmations on ropes — net as community archive | Concept |
| 📊 **Data Logging**     | Heat maps of usage patterns                               | Concept |
| 💡 **LED Feedback**     | WS2812B strip — light pulses from touched rope            | Concept |
| 🎙️ **Recording**        | "Record" button saves last 30s                            | Concept |
| 🔊 **Spatial Audio**    | Multi-speaker positional sound                            | Concept |
| 🎢 **Guerilla Install** | Playground or atrium pop-up (needs 2nd MCU)               | Parked  |

### Industry & Academic Paths

| Path                     | Target                           | Opportunity                                         |
| ------------------------ | -------------------------------- | --------------------------------------------------- |
| 🎡 **Musical Playground** | KOMPAN, playground manufacturers | Outdoor, weatherproof, kid-safe rope structures     |
| 🎨 **Art Installation**   | Ars Electronica, transmediale    | Residencies, collective performances                |
| 📄 **Publication**        | NIME, TEI, DIS                   | Restorative design, dual affordances, Ma aesthetics |

## 📎 Appendix

### Project Files

```
seilnetz/
├── index.html       # Web app (Tone.js + Three.js)
├── midi-debug.html  # MIDI diagnostics
├── README.md        # This document (SSOT)
├── ABSTRACT.md      # IMRaD abstract (German)
├── NOTES.md         # Meeting notes archive
└── images/          # Reference photos
```

### External Resources

| Resource                | Location                                | Purpose                                              |
| ----------------------- | --------------------------------------- | ---------------------------------------------------- |
| **FigJam Canvas**       | [Figma](https://www.figma.com/)         | Visual moodboard, construction ideas, process photos |
| **Monochord Reference** | [YouTube](https://youtu.be/c1aCNMIZ5lM) | Harp sound inspiration                               |

### References

- [Tomás Saraceno](https://studiotomassaraceno.org/) — Spider/Web installations
- [ESP32 BLE-MIDI](https://github.com/lathoub/Arduino-BLE-MIDI)
- [Tone.js](https://tonejs.github.io/) — Web audio
- [Three.js](https://threejs.org/) — 3D visualization
