# Sonic Prosthesis: Nervensystem
**Course:** Perspectives in Design — Robotic Renovation  
**Team:** Antonia, Lilian, Mate, Vincent



## The Renovation Question

> *"What happens when we not only use technologies for renovation, but rather adapt and alter, when we manipulate and mess with them towards unknown outcome?"*  
> — Course Brief

**Our Answer:** We give the existing net structure a **nervous system** — the ability to feel touch and respond with sound. This is not replacement, but **augmentation**: a sonic prosthesis that transforms passive furniture into an interactive instrument.


## 1. Concept: From Furniture to Instrument

### The Situation
The Alter Lesesaal contains a suspended rope net — a chill-out space where students sit, recline, and gather. It's comfortable but **mute**. It absorbs human presence without acknowledgment.

### The Intervention
We add **sensory capability** through embedded piezo sensors, transforming the net into a giant playable string instrument. The net becomes a **Nervensystem** — a nervous system that:
- **Feels** vibration and touch
- **Responds** with harmonious sound
- **Invites** participation and play

### Inspiration: Tomás Saraceno
Saraceno's "Space Nets" and spider web installations demonstrate how tensile structures can become instruments of connection — between bodies, between species, between scales. Our work applies this thinking to renovation: **what latent capabilities exist in existing structures?**


## 2. Design Principles

### A. Prosthetic Thinking
The intervention is **additive, not destructive**. The net remains fully functional as seating. The sensors and wiring are:
- Removable
- Non-invasive (tape, not glue)
- Hidden within the structure

### B. Harmonic Constraints
To ensure the sonic output is always pleasant (even with chaotic input), we use **musical guardrails**:
- **Pentatonic Scale:** Any combination sounds good
- **Slow Attack:** Sounds swell rather than beep
- **Long Release:** Notes blend into ambient wash

### C. Participation Spectrum
The system rewards both:
- **Passive presence:** Sitting creates subtle drones
- **Active play:** Plucking triggers melodic notes


## 3. System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    PHYSICAL LAYER                           │
│   User → Rope → Vibration → Piezo Sensor → Voltage Spike    │
└─────────────────────────┬───────────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                    DIGITAL LAYER                            │
│   ESP32: Threshold → Debounce → MIDI Note (BLE)             │
└─────────────────────────┬───────────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────┐
│                    SOUND LAYER                              │
│   Browser/Ableton: MIDI → Synthesis → Speakers              │
└─────────────────────────────────────────────────────────────┘
```

### Hardware
| Component           | Choice                | Rationale                    |
| ------------------- | --------------------- | ---------------------------- |
| **Microcontroller** | ESP32 (WROOM)         | Built-in BLE MIDI, no cables |
| **Sensors**         | Piezo elements (x2-6) | Cheap, sensitive, robust     |
| **Power**           | USB battery pack      | Hidden in truss structure    |

### Software
| Layer             | Implementation     | Purpose                          |
| ----------------- | ------------------ | -------------------------------- |
| **Firmware**      | Arduino + BLE-MIDI | Sensor → MIDI translation        |
| **Synthesis**     | Tone.js (Browser)  | Portable, zero-install demo      |
| **Visualization** | Three.js           | 3D net mirrors physical triggers |


## 4. Process & Methodology

### Phase 1: Research & Inspiration
- Study of Tomás Saraceno's tensile works
- Analysis of existing net structure (rope types, tension points)
- Sound design exploration (what should a "net" sound like?)

### Phase 2: Prototyping
- Single-sensor proof of concept
- BLE MIDI communication testing
- Sound palette development (scales, envelopes)

### Phase 3: Integration
- Multi-sensor deployment on physical net
- Web-based visualization for remote demo
- Calibration and threshold tuning

### Phase 4: Documentation
- Process photography
- Technical documentation
- Presentation canvas (Figma)


## 5. Midterm Deliverable

### Physical Installation
- The net with embedded sensors (2 channels active)
- Wireless connection to sound station
- Visitors can sit, touch, pluck

### Digital Twin
- `index.html`: Browser-based 3D visualization + sound engine
- Real-time response to MIDI from physical net
- Standalone demo mode for presentations

### Documentation
- Design Canvas (Figma): Inspiration → Process → Outlook
- This document (DESIGN_DOC.md)
- Video documentation of interaction


## 6. Outlook: Future Scenarios

### Immediate (Post-Midterm)
- Expand to 6 sensors covering full net
- Refine debounce/threshold on ESP32
- Add ambient "breathing" drone layer

### Medium-Term
- Spatial audio (sounds from different net positions)
- Multiple simultaneous users creating polyphony
- Generative evolution (soundscape shifts over hours)

### Long-Term Vision
- Apply to other renovation contexts (scaffolding, fences, bridges)
- Open-source toolkit for "sonic prosthetics"
- Collaboration with Saraceno or similar artists


## 7. Technical Notes (Dec 2024)

### Current Configuration
- **Hardware:** "Paracord-Drums" ESP32 controller
- **Protocol:** MIDI Channel = Sensor Index (Ch1 → Sensor 0, Ch2 → Sensor 1)
- **Web App Debounce:** 150ms (safety net for firmware issues)

### Known Issues
| Issue                     | Cause               | Fix Location      |
| ------------------------- | ------------------- | ----------------- |
| Velocity floor ~50        | ESP32 `map()` range | Firmware          |
| Multiple triggers per hit | Piezo ringing       | Firmware debounce |
| Ghost Channel 3           | Floating pin        | Hardware/wiring   |

### Files
```
seilnetz/
├── index.html       # Web app (Tone.js + Three.js)
├── midi-debug.html  # MIDI diagnostics console
├── DESIGN_DOC.md    # This document
└── README.md        # Setup instructions
```

## References

- Tomás Saraceno: [https://studiotomassaraceno.org/](https://studiotomassaraceno.org/)
- ESP32 BLE-MIDI Library: [https://github.com/lathoub/Arduino-BLE-MIDI](https://github.com/lathoub/Arduino-BLE-MIDI)
- Tone.js: [https://tonejs.github.io/](https://tonejs.github.io/)
- Three.js: [https://threejs.org/](https://threejs.org/)
