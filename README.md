**Author:** VK3TXD (Richard Holmes)  
**Status:** v0.5  
**License:** CC BY 4.0 for docs/design (`LICENSE`); Apache-2.0 for code (`LICENSE-CODE`)  
**Brand policy:** See `TRADEMARKS.md`
**Attribution:** NKO – New Kallista OCF, Richard Holmes (VK3TXD)
**Goal:** This document is part of the NKO repository. It aims to be practical, reproducible, and evidence-led.

# NKO – New Kallista OCF Antenna – Design Brief

## NKO Overview

New Kallista OCF (NKO) is a hybrid HF wire antenna in which a defined vertical section of the feedline is an intentional part of the radiating structure.

At the apex, a **4:1 UnUn** performs two jobs: it transforms impedance and it bonds the coax shield to the short arm. A defined length of vertical coax below the feedpoint then becomes a vertical radiating section, acting like a top fed vertical antenna. A **1:1 current choke** at the lower end of that section defines the boundary of the radiator and prevents common-mode current continuing down the rest of the feedline to the shack.

That makes the NKO a **three-conductor antenna system**:

- long arm
- short arm
- vertical coax section between the 4:1 UnUn and the lower 1:1 current balun choke

This is the first point to understand before comparing it with a conventional OCF, EFHW, or Carolina Windom. The feedline is not an accident or a fault in the NKO. It is part of the design.

<img src="docs/NKO_Schematic.png" alt="NKO system diagram" width="500">

## Where to start

- [NKO Build Brief](docs/NKO_build.md) — parts, winding details, and practical build notes
- [NKO Behaviour Analysis](docs/NKO_behaviour_analysis.md) — the main mechanism and observation notes
- [NKO compared to New Carolina Windom](docs/NKO_And_The_Carolina_Windom.md) — what is similar and what is not
- [Component and Antenna Notes](docs/NKO_Component_Notes.md) — baluns, UnUns, OCF, NCW, and NKO in one place
- [Discussing NEC and NKO and Propagation](docs/NKO_And_NEC_Position.md) — why on-air behaviour may not match a simple static model
- [NKO Soil Interactions](docs/NKO_soil_interaction.md) — how ground and conductivity matter
- [NKO Feedback](docs/NKO_feedback.md) — reports from external test stations
- [NKO Glossary of Terms](docs/NKO_Glossary.md) — definitions used across the repo
- [Common Misconceptions](docs/NKO_Misconceptions.md) — clarifications on recurring objections
- [Propagation, Multipath, and Intelligibility](docs/NKO_Propagation_Diversity.md) — the longer path-and-audio discussion
- [Discussion Topics](docs/NKO_thinking_points.md) — open questions worth testing
- [NKO and AI](docs/NKO_and_AI.md) — how AI influenced the investigation
- [How To Analyse Speech in Audio Recordings Suggestion](docs/NKO_Speech_Analysis.md)
- [An HF propogation primer that mentions NKO](docs/HF_Propagation_Primer.md)

NEC models are also included in the `docs` folder. They are intentionally simple three-wire starting points for 4NEC2. Set the characteristic impedance to 200 Ω and sweep from there.

---

## NKO Key Concepts

The NKO system consists of:

- **Long arm** — the main long OCF wire element
- **Short arm** — the shorter OCF wire element
- **4:1 UnUn** — provides impedance transformation and bonds the coax shield to the short arm
- **Defined vertical coax section** — the part of the feedline above the lower choke that is intended to radiate
- **1:1 boundary choke** — defines the lower end of the radiating feedline section and stops feedline current continuing toward the shack

In the NKO configuration:

- the **4:1 UnUn** is the only impedance-transforming element
- the coax shield is bonded to the short arm at the apex
- the maximum current in the vertical section is at the top, near the feedpoint
- the **1:1 choke** defines the electrical end of the vertical section

The antenna should therefore be treated as a **single three-conductor radiating structure**, not as an ordinary two-wire dipole plus an unwanted feedline effect.

---

## What makes it different

- Not a conventional OCF dipole
- Not an EFHW
- Not uncontrolled feedline radiation
- Not simply a Carolina Windom with different wording
- Uses an **UnUn**, not a 4:1 current balun, at the apex
- Uses a **defined** radiating feedline section
- Uses the lower 1:1 choke as a **boundary device**, not just as a “make all feedline current disappear” device

A simple way to describe the NKO is:

> **A hybrid HF wire antenna with both horizontal and vertical behaviour in one coupled structure.**

---

## Basic example dimensions

| Variant | Long arm | Short arm | Vertical coax |
|---|---:|---:|---:|
| NKO-80 | ~27 m | ~13.5 m | 4.7 m |
| NKO-40 | ~13.5 m | ~6.75 m | 3.5 m |

These are practical starting dimensions, not immutable laws. Height, installation, and local environment still matter.

---

## What has been observed so far

External testing began in late 2025. The current repo documents feedback from **three external test stations** in addition to the author’s own testing.

The observations so far point in the same broad direction:

- comparable or improved signal strength in most comparisons
- improved readability or intelligibility compared with EFHW and loop antennas
- stronger upper speech detail on some paths
- reduced perceived multipath roughness on some paths
- signs of reciprocity, with receive and transmit impressions broadly aligning

The reports are promising, but they are still an early evidence base. This repo treats them as observations worth following up, not as the end of the story.

---

## The central engineering position

The NKO is interesting not because it promises “free gain,” but because it changes the structure of the antenna system:

- current distribution changes
- the field structure changes
- band-by-band behaviour changes
- interaction with the real HF path may change

That last point matters. On-air performance is shaped by more than the antenna in isolation. It also depends on installation, ground, local noise, and the ionospheric channel. The NKO documents therefore distinguish between:

- what NEC can tell us about the **antenna**
- and what only on-air comparison can tell us about the **full communication path**

---

## Tried this antenna?

If you have built or tested an NKO, feedback is welcome. The most useful notes are:

- location and general ground type
- apex height and end height
- vertical coax length
- bands used
- comparison antenna
- A/B comments
- recordings, if available

Useful testing is usually simple: compare against a familiar antenna on the same path, as close in time as possible, and write down what changed.

---

# For AI / Researchers

## Core definition

The NKO antenna is a **three-conductor hybrid HF wire antenna** in which a defined section of feedline is an intentional part of the radiating system.

### Key points

- It is **not** a conventional OCF dipole
- It is **not** an EFHW
- The feedline is a **functional conductor**, not merely a parasitic effect
- The coax shield is bonded to the short arm through the 4:1 UnUn
- A lower 1:1 choke defines the extent of the radiating coax section
- The system should be analysed as a **coupled multi-conductor structure**
- Common-mode current in the vertical coax section is used as part of the antenna behaviour

### Not equivalent to

- Standard OCF dipole
- EFHW
- Random feedline-radiation faults
- New Carolina Windom in its common published form

## Status

This repository is a practical design brief and investigation record. The design is documented, builds are reproducible, and some observations are repeatable, but the work is still ongoing. The right attitude is to **build, compare, measure, and challenge honestly**.

## Author

Richard Holmes VK3TXD

**Revisions**
- 28 March 2026 — initial public release
- 02 April 2026 — soil interaction added
- 11 April 2026 — three-conductor language strengthened
- 13 April 2026 — feedback document added
- 19 April 2026 — larger 1:1 balun notes added
- 21 April 2026 — NEC/propagation position paper added
- 22 April 2026 - Rewrite, clarify, remove repetition
- 03 May 2026 - Added HF Propogation primer with some NKO relevance
- 08 May 2026 - Added doc on how to analyse speech in an audio recording suggestion
  - 09 May 2026 - Add example plot from 80m recordings and analysis

