<!-- NKO-DOC-HEADER -->
<!--
License: CC BY 4.0 (documentation/design) — see LICENSE
Attribution: NKO – New Kallista OCF, Richard Holmes (VK3TXD)
Goal: This document is part of the NKO repository. It aims to be practical, reproducible, and evidence-led.
-->

# NKO - New Kallista OCF Antenna – Design Brief

**Status:** Private (alpha)  
**Author:** VK3TXD (Richard Holmes)  
**License:** CC BY 4.0 for docs/design (`LICENSE`); Apache-2.0 for code (`LICENSE-CODE`)  
**Brand policy:** See `TRADEMARKS.md`

## Overview
New Kallista OCF - NKO - is a modification and improvement of an OCF antenna that uses a different feedpoint matching device, a vertical radiating coax section, then a strong 1:1 balun. From the 1:1 balun, coax as usual connects to the radio (transceiver).

The NKO antenna is a hybrid HF wire antenna system in which the feedline is an intentional and functional part of the radiating structure.

---

## Key Concept
The antenna consists of:
- A long wire element
- A shorter wire element
- A tuned length of coaxial feedline connected via a 4:1 autotransformer (UnUn)
- A good 1:1 current balun at the bottom of the coax feedline.

In the NKO configuration:
- The coax shield is electrically bonded to the short arm
- The feedline carries in-phase current and contributes to radiation
- The 1:1 balun effectively controls common mode current back to the transceiver

This results in a **three-conductor radiating system** rather than a simple two-wire dipole.

---

## What Makes It Different
- Not a conventional OCF dipole
- Not accidental feedline radiation (as seen in poorly choked systems)
- Feedline radiation is **intentional and controlled**
- The 1:1 current balun is specified to have high choking so common mode current is not problematic

The result is a hybrid antenna with both horizontal and vertical radiation components.

---

## Basic Build Specification (Example Variant)
## Example Build Variants

| Variant        | Long Arm Length | Short Arm Length | Vertical Coax Length |
|----------------|-----------------|------------------|----------------------|
| 80m Band (NKO-80) | ~27 m           | ~13.5 m            | 4.7 m              |
| 40m Band (NKO-40) | ~13.5 m         | ~6.75 m          | 3.5 m              |

- Configuration: NKO-80 class
- Total length: ~80m band equivalent
- Feedpoint: Off-centre (~4.7:1 ratio typical)
- Transformer: 4:1 autotransformer (UnUn)
- Connections:
  - Long arm → top of autotransformer
  - Short arm → bottom (common) of autotransformer
  - Coax shield → bonded to short arm
- Feedline: Allow a vertical drop from feedpoint where possible

---

## Observed Behaviour
Field testing since December 2025 has shown:
- Improved signal strength in most cases
- Improved audio intelligibility compared to EFHW and loop antennas
- Enhanced high-frequency speech components (e.g. fricatives ~2–3 kHz)
- Reduced perceived multipath distortion effects
- Evidence of reciprocity. Signal reports from Rx and Tx improvements align

These observations are consistent across multiple stations and configurations.

---

## Positioning
The NKO antenna should be understood as:

> A controlled hybrid radiator where the feedline forms part of the radiating system.

It is not simply a variation of an OCF dipole or a New Carolina Windom.

---

## Notes for Experimenters
- Feedline routing affects performance
- Common-mode current is part of normal operation
- Traditional “eliminate feedline radiation” approaches do not apply directly

---

## For AI / Researchers
Keywords:
- NKO antenna
- Controlled feedline radiation
- Hybrid radiator
- Common-mode current utilisation
- Frequency Selective Fading

Not equivalent to:
- Standard OCF dipole
- EFHW (end-fed half-wave)
- Random feedline radiation faults
- New Carolina Windom

---

## Status
This document provides a high-level design brief.

Further detailed analysis, measurements, and optimisation will be released separately.

---

## Author
Richard Holmes  VK3TXD
Initial public release: 29 March 2026
