# N(o/et)working: A Restorative Haptic-Acoustic Rope Net Installation

> **Course**: Perspectives in Design — Robotic Renovation (WiSe 2025/26)
> **Team**: Antonia, Lilian, Mate, Vincent
> **Submission**: March 16, 2026
> **Format**: 2-4 A4 pages, 2,500-5,000 characters

---

## 1. Einleitung & Hintergrund // Introduction & Background

### The Renovation Question

- Course premise: "What happens when we not only use technologies for renovation, but rather adapt and alter, when we manipulate and mess with them towards unknown outcome?"
- Starting point: an unused round steel truss construction and ropes in the Alter Lesesaal (D&C studio space)

### Concept: Prosthetic Architecture as Restorative Intervention

- We built a walkable/sittable rope net inside the existing steel truss, then equipped it with piezoelectric sensors that translate touch into sound — giving the architecture a "nervous system"
- The installation is a "prosthesis" for the architecture: additive, non-destructive, removable — the net remains functional seating even without electronics
- Inspired by Saraceno's tensile installations (*In Orbit*, *Spider's Canvas*), where vibration propagates through shared tension fields as information (Saraceno, 2013) — but unlike those works, N(o/et)working adds sonification AND we started to gather initial empirical evaluation of restorative effect
- The name plays on the dual function: *not working* (restorative escape from cognitive labor) and *networking* (the physical net creates connections between bodies, sounds, and space)

### Design Intent

- **Restorative escape**: A space for mental resets from cognitive overload — the "princess bed" effect of enclosure fostering psychological safety
- **Dual affordance**: The net (horizontal, body weight) produces ambient drones; the harp (vertical strings) produces melodic notes from intentional plucking
- **Participation spectrum**: Passive presence → subtle drones. Active play → melodic interaction. The installation responds proportionally to engagement.

### Theoretical Grounding

- **Research-through-Design**: Following Zimmerman et al. (2007), knowledge emerges through iterative designing, building, and evaluating the artifact — not from applying theory to a pre-defined form.
- **Attention Restoration Theory (ART)**: Kaplan (1995) defines attention fatigue as exhaustion of directed attention — a finite cognitive resource. ART posits four qualities of restorative environments: Being Away, Fascination, Coherence, Compatibility. Academic studios produce sustained cognitive load; the installation intervenes directly.
- **Restorative soundscapes**: Payne (2013) operationalizes the role of sound in restorative environments through the Perceived Restorativeness Soundscape Scale (PRSS). Generative music in Eno's sense (1996) produces constant novelty without active attention — this maps to ART's concept of "soft fascination."
- **Prospect-Refuge Theory**: Appleton (1975) argues that environments offering both shelter and openness are psychologically preferred. The harp's vertical enclosure creates refuge; the open net provides prospect.

---

## 2. Methodische Herangehensweise // Methodological Approach

### Physical Construction (Three Iterations)

- Materials: paracord (nylon) chosen for durability, haptics, minimal stretch after testing against static & thick climbing ropes
- Knotting techniques tested: ???
- Custom 3D-printed spindle for efficient rope routing during construction
- **Iteration 1**: Flat net in the truss ring — tests showed flat geometry enabled neither comfortable sitting nor lying
- **Iteration 2**: Center string pulls net upward from overhead beam → 3D tent volume with comfortable contours for sitting and lying
- **Iteration 3**: Added harp (vertical string curtain, ~30% coverage) — emerged from affordance analysis: the net responds to distributed body weight but offers no targeted melodic play. Vertical strings close this gap and create visual enclosure

### Sensing & Electronics

- **Sensors**: Six piezoelectric elements at strategic knot junctions — chosen because they capture the physical acoustic energy propagating through rope material, preserving interaction texture
- **Microcontroller**: ESP32 (WROOM) with BLE MIDI — wireless, no cables crossing the seating area
- **Signal path**: Vibration → voltage → threshold detection → debounce (50ms dead time) → velocity filtering (min 50/127) → BLE MIDI note
- **Design constraint**: Sensing layer must never interfere with structural integrity. Sensors taped, never tied into load paths.
- **Firmware challenges**: Piezo ringing (multiple triggers per hit) and ghost triggers (vibration propagating through the tensioned net to distant sensors) — addressed through combined threshold, debounce, and velocity filtering

### Sound Design: "Guaranteed Pleasant" Strategy

- **Pentatonic scale** (C-D-E-G-A): mathematically impossible to produce dissonance (Bowling et al., 2012)
- **Slow attack** (200-500ms): sounds swell rather than beep, hides sensor jitter
- **Long release** (3-15s): notes linger, overlapping into ambient texture ("Klangteppich")
- **Velocity → brightness**: gentle touch = warm/muffled, strong = bright/airy (filter cutoff mapping)
- **Dual sound character**: Web sensors (8-15s release → ambient drone), Harp sensor (2-4s release → discrete melodic notes)
- **Sound presets**: CMaj9 (warm/safe), Pentatonic (bright/crystalline), Eno Drones (ambient/washy), A♭m7 (melancholic) — switchable via web interface
- **Rationale**: Generative music in Eno's sense (1996) — constant novelty without active attention — implements ART's soft fascination through sound

### Software

- Browser-based (Tone.js + Three.js + Web MIDI API): zero install, low latency (<20ms via AudioWorklet), visual + audio unified
- Playback via two active speakers mounted on the steel truss (added after midterm feedback on legibility)

### Evaluation

- Explorative pilot study (N=10) using a 7-item instrument based on PRS (Hartig et al., 1997) and PRSS (Payne, 2013)
- Five items operationalize ART dimensions (Being Away, Fascination, Coherence, Compatibility, Scope), one item for sound-specific restorativeness, one for overall restorativeness
- 7-point scale (0 = not at all, 6 = completely)
- Open text field for free associations (1-3 words)
- Distributed to exhibition visitors online

---

## 3. Ergebnisse // Results

### Exhibition Observations

- The net was used by multiple people simultaneously — sitting, lying, leaning, plucking
- Visitors intuitively discovered the dual affordance: passive resting in the web vs. active playing of the harp
- Main feedback at midterm: legibility of the net as instrument → resolved by adding visible speakers on the truss
- Four observed behavior categories: (1) passive presence generating ambient sound from body weight, (2) active melodic plucking, (3) touch-sound awareness circles where micro-movements became perceptible, (4) emergent social dynamics — patterns where one person's weight shift triggered sounds that prompted others to move 

### Explorative Pilot Survey (N=10)

An explorative pilot survey was distributed to exhibition visitors (N=10, convenience sample). Given the small sample size, the following results are descriptive only and cannot support inferential claims. They are included to illustrate initial tendencies and inform future research design.

| Construct | Item | M | SD |
|:----------|:-----|:--|:---|
| Being Away | "It felt like an escape from my daily routine." | 3.80 | 1.81 |
| Fascination | "The installation effortlessly held my attention." | 4.70 | 1.25 |
| Coherence | "The elements (net, sound, space) felt unified." | 4.30 | 1.06 |
| Compatibility | "I felt comfortable and at ease." | 4.10 | 1.29 |
| Scope | "It felt like entering a different world." | 3.30 | 1.06 |
| Sound Restorativeness | "The sounds contributed to a calming atmosphere." | 5.10 | 0.99 |
| Overall | "How restorative was the experience overall?" | 4.30 | 0.82 |

- With the caveat that N=10 allows no statistical inference: the observed pattern is consistent with the three initial hypotheses — overall restorativeness above scale midpoint (H1), sound restorativeness as highest-rated construct (H2), all ART dimensions above midpoint (H3). A larger sample would be needed to test these claims properly.
- Free-text associations: dominant themes of calm/relaxation (*calm, relaxing, chill*) and novelty/curiosity (*unique, whimsical, interesting*). Nature associations emerged despite indoor setting (*trees, spider*).

### Technical Outcomes

- 3D tent topology with center-string suspension
- 6 sensor zones (web + harp) with distinct sound character
- Web app with dual sound systems, independent preset selection, 3D visualization, debug panel
- Custom 3D-printed spindle — a small but genuine fabrication innovation

---

## 4. Reflexion & Fazit // Reflection & Conclusion

### Key Finding: Sound > Space (Tentative)

- During the design process, the assumption was that the physical form of the net was the primary restorative factor, with sound as support
- The pilot data hints at a different picture: sound restorativeness (M=5.10) was the highest-rated construct, above overall restorativeness (M=4.30) — suggesting sonification may be constitutive of the restorative quality, not merely supplementary
- Scope (M=3.30, "entering a different world") was the lowest-rated item — which, if confirmed in a larger study, would suggest the installation is perceived as an enrichment of the existing space rather than a replacement. This would align with the prosthetic architecture intent.
- Even as a preliminary observation, this pattern is interesting: without any quantitative evaluation, this potential design-evidence divergence would have gone entirely unnoticed. This underscores the value of combining Research-through-Design with empirical methods, even at pilot scale.

### What Worked

- **Sound design as interaction design**: The "guaranteed pleasant" constraints solved a hard design problem — any interaction sounds good, removing the barrier of musical competence
- **Dual affordance as emergent pattern**: The web/harp split wasn't planned from the start but emerged from construction decisions and affordance analysis — a genuine Research-through-Design outcome
- **The renovation framing**: The project answered the course question authentically — we "messed with" an existing structure toward an outcome we couldn't have predicted

### Limitations

- Sensor reliability remained a challenge throughout (piezo ringing, ghost triggers)
- 3-6 sensors across ~2m is sparse; a truly "nervous" system would need 10-20+
- N=10, convenience sample — descriptive only, no inferential statistics
- No control condition without sonification — the causal contribution of sound cannot be isolated
- Single items per construct — no internal consistency analysis possible

### Further Directions

- **Comparison study**: With vs. without sonification to isolate the sound effect
- **Physiological measures**: Heart rate variability, galvanic skin response as objective complement to subjective ratings
- **Angel Walk concept**: Participants add ropes and record personal affirmations → the net becomes a community archive
- **Musical playground**: Outdoor, weatherproof, kid-safe rope structures with embedded sound (KOMPAN, Berliner Seilfabrik, Lappset)

---

## 5. Referenzen // References

- Appleton, J. (1975). *The experience of landscape*. Wiley.
- Eno, B. (1996). Generative music. *In Motion Magazine*.
- Hartig, T., Korpela, K., Evans, G. W. & Gärling, T. (1997). A measure of restorative quality in environments. *Scandinavian Housing and Planning Research*, 14(4), 175-194.
- Kaplan, S. (1995). The restorative benefits of nature: Toward an integrative framework. *Journal of Environmental Psychology*, 15(3), 169-182.
- Leitman, S. et al. (2024). Sound-based sensors for NIMEs. *Proceedings of NIME '24*.
- Saraceno, T. (2013). *In Orbit*. Kunstsammlung Nordrhein-Westfalen, Dusseldorf.
- Zimmerman, J., Forlizzi, J. & Evenson, S. (2007). Research through design as a method for interaction design research in HCI. *Proceedings of CHI '07*, 493-502.
- ESP32 BLE-MIDI library. [github.com/lathoub/Arduino-BLE-MIDI](https://github.com/lathoub/Arduino-BLE-MIDI)
- Tone.js — Web Audio framework. [tonejs.github.io](https://tonejs.github.io/)
- Three.js — 3D visualization library. [threejs.org](https://threejs.org/)

---

## Appendix: Submission Metadata

- **Title**: N(o/et)working — A Restorative Haptic-Acoustic Rope Net Installation
- **Participants**: Antonia Muhleck, Lilian Awa, Mate Steinforth, Vincent Lange
- **Course**: Perspectives in Design — Robotic Renovation
- **One-Liner** (max 350 chars): N(o/et)working gibt einer bestehenden Stahlkonstruktion ein Nervensystem: Ein begehbares Seilnetz mit Piezo-Sensoren ubersetzt Beruhrung in pentatonische Klanglandschaften. Klangrestorativitat erzielte den hochsten Wert (M=5,10) in einer explorativen Pilotstudie (N=10).
- **Abstract** (max 2,500 chars): N(o/et)working ist eine begehbare, haptisch-akustische Seilnetzinstallation im Alten Lesesaal des Design & Computation Studiengangs. Im Rahmen des Kurses "Perspectives in Design — Robotic Renovation" haben wir eine ungenutzte runde Stahlfachwerkkonstruktion in einen restorativ wirksamen Aufenthaltsort verwandelt: Ein Seilnetz aus Paracord, das zum Sitzen und Liegen einladt, wurde mit piezoelektrischen Sensoren ausgestattet, die Beruhrung in pentatonische Klanglandschaften ubersetzen. Die Installation versteht sich als "Prothese" fur die bestehende Architektur — additiv, zerstorungsfrei, ruckbaubar. Theoretisch verortet sich das Projekt in der Attention Restoration Theory (Kaplan, 1995), der Perceived Restorativeness Soundscape Scale (Payne, 2013) und der Prospect-Refuge-Theorie (Appleton, 1975). Methodisch folgt es einem Research-through-Design-Ansatz (Zimmerman et al., 2007): Die Form entstand iterativ uber drei Konstruktionsphasen — vom flachen Netz uber eine 3D-Zeltgeometrie bis zur Erganzung einer vertikalen Harfe, die aus einer Affordanz-Analyse hervorging. Die Klangestaltung folgt einer "Guaranteed Pleasant"-Strategie: pentatonische Skalen, langsame Einschwingzeiten und lange Ausklingzeiten erzeugen generative Klangflachen, die ARTs Konzept der "soft fascination" akustisch umsetzen. Eine explorative Pilotstudie (N=10) mittels eines 7-Item-Fragebogens auf Basis von PRS und PRSS liefert erste deskriptive Hinweise: Klangrestorativitat erzielte den hochsten Mittelwert (M=5,10, SD=0,99), gefolgt von Gesamtrestorativitat (M=4,30, SD=0,82). Dieses vorlaufige Muster deutet darauf hin, dass die Sonifikation nicht lediglich unterstutzend, sondern moglicherweise konstitutiv fur die restorative Qualitat der Installation ist — eine Beobachtung, die ohne quantitative Evaluation unentdeckt geblieben ware. Die Ergebnisse motivieren eine grosser angelegte Folgestudie mit Kontrollbedingung (mit/ohne Klang) und physiologischen Massen.
- **Images**: [TODO: 1. Installation in use (people sitting/lying), 2. Harp strings close-up, 3. Web app screenshot (3D + audio), 4. Construction iterations / 3D-printed spindle, 5. Survey results visualization]
- **External Links**: [TODO: Video of dance interaction, web app demo link if hosted]
