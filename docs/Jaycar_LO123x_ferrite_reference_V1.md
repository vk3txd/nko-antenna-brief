# Jaycar LO123x Ferrite Core Reference (LO1230 / LO1234 / LO1238)

Consolidated: 2026-06-19
Purpose: a single reusable reference for the Jaycar/Electus LO123x toroids, so the same details (dimensions, material constants, AL, flux/thermal behaviour) do not have to be re-searched each session.

This will save AI some search and analysis time and make results more consistent. Load it into AI project sources / notes.

This merges:

- the previous NKO reference notes,
- Jaycar's **published** *FERRITES* reference data sheet (the L8 material constants that were previously missing),
- amateur-radio measurements (VK1HW/VK5HW, VK1OD),
- prior NKO project test notes,
- geometry-derived estimates,
- a worked explanation of why a high-µ MnZn core can still be efficient in a 4:1 UnUn.

It is **not** a manufacturer-grade RF datasheet. Confidence is labelled throughout.

> **Core caution (unchanged):** Jaycar/Electus labels such as **L8** and **L15** are product identifiers, not full material specifications. Treat published constants as nominal, expect wide tolerance, and measure the actual batch when the value matters.

---

## 0. What changed in this version (read first)

Two substantive updates over the previous notes:

1. **Added real L8 material constants** (Section 2) from Jaycar's published *FERRITES* reference data sheet — initial permeability, saturation flux density, residual flux density, loss factor, and (lower-confidence) Curie temperature / density. This is the data the old file noted as missing. L15 (LO1238) material data is still **not** publicly available; only a community permeability measurement exists.

2. **Corrected the flux-stress "equivalent power" column** (Section 8). Winding confirmed: two wires side by side, 7 passes through the core = bifilar, **7 turns per wire**. In this standard Ruthroff 4:1 the 50 Ω input sits across **one** 7-turn wire; the 200 Ω side is both wires in series (**14 turns**) at twice the voltage. So the flux-setting winding is the 7-turn / 50 Ω one, and equivalent power is `V_50² / 50`. The previous notes paired the 200 Ω-side voltage with 7 turns, which doubled the calculated flux and understated equivalent power by **4×** — those figures are superseded. Headline conclusion unchanged: **flux at any realistic power is far below saturation; heating is the limit, not saturation.**

---

## 1. Quick identification table

| Part | Jaycar/Electus description | Material label | OD | ID | Height | Pack | Confidence |
|---|---|---:|---:|---:|---:|---:|---|
| LO1230 | L8 18 × 10 × 6 mm toroid/ring core | L8 | 18 mm | 10 mm | 6 mm | 6 | High |
| LO1234 | L8 25 × 15 × 10 mm toroid/ring core | L8 | 25 mm | 15 mm | 10 mm | 4 | High |
| LO1238 | L15 35 × 21 × 13 mm toroid/ring core | L15 (some product-page fields conflict) | 35 mm | 21 mm | 13 mm | 2 | Medium |

### LO1238 material-label caution

The Jaycar LO1238 title/overview reads `L15 35x21x13mm Toroid (or Ring) Cores` / `MATERIAL L15 SIZE A35 X B21 X C13`, but at least one on-page specification block has shown copied/inconsistent fields (`Toroid L8`, `25 mm`, `15 mm`, `10 mm`).

> Treat LO1238 as physically **35 × 21 × 13 mm**, commonly labelled **L15**, but do **not** assume a fully-known material curve. Do **not** assume Jaycar `L15` equals Fair-Rite `15` — name similarity is not equivalence.

---

## 2. Material constants

### 2.1 L8 (LO1230, LO1234) — from Jaycar's published *FERRITES* reference data sheet

L8 is a **Mn-Zn (manganese-zinc) ferrite** — a high-permeability material optimised for low-frequency / suppression use. (Jaycar's data sheet states their toroid range is generally Mn-Zn.) Measured on a 30.8 × 18.4 × 7.5 mm test toroid, 0.5 mm UEW, 47 turns, 25 °C; initial-permeability test at 10 kHz / 0.8 mA.

| Property | Symbol | Value | Confidence |
|---|---|---|---|
| Material family | — | Mn-Zn ferrite | High |
| Initial permeability | µi | **1500 ±20%** (at 10 kHz) | High |
| Saturation flux density | Bs | **2550 G ≈ 0.255 T** | High |
| Residual flux density | Br | 1225 G ≈ 0.1225 T | High |
| Relative loss factor | tan δ / µi | < 2.8 × 10⁻⁵ at **0.3 MHz** | High |
| Coercive force | Hc | ≈ 0.225 Oe (soft, low-loss) | Medium |
| Curie temperature | Tc | > 120 °C | Medium |
| Density | d | ≈ 5.0 g/cm³ | Medium |
| Resistivity | ρ | low — Mn-Zn typically ~10–10³ Ω·cm | Qualitative |

Notes:

- **Loss factor is specified only up to 0.3 MHz.** That is the tell that L8 is characterised for LF/MF. Its permeability rolls off, and µ″ (loss) rises, above roughly a few hundred kHz. By 7 MHz it is well into the lossy region as a *material*.
- This is the conventional reason hams reach for **Ni-Zn type 43 or 61** for HF baluns/ununs instead of Mn-Zn. See Section 4 for why L8 nonetheless tests well in a 4:1 UnUn at 7 MHz.
- The Medium-confidence rows (Hc, Tc, density) were read from a scanned sheet; they are physically consistent with a high-µ Mn-Zn ferrite but should be verified against the original PDF if used for a margin decision.

### 2.2 L15 (LO1238) — no published material data

No manufacturer material curve is publicly available (the Jaycar reference sheet covers L8, J70, M7, S1H — not L15). The only data point is a community measurement:

- VK1OD: initial permeability **≈ 1100 at 10 kHz** — i.e. somewhat lower µi than L8. That hints at a different high-permeability suppression material, but it is not enough to define an RF loss curve.

A separately quoted "AL ≈ 145 nH" for LO1238 is **inconsistent** with µi ≈ 1100 and the larger cross-section (it would imply far lower AL than L8, which is not plausible on geometry). Treat that AL figure as unreliable.

> For L15: known physical size, probable µi order ~1100, everything else **measure on the batch**.

---

## 3. Geometry-derived values

Derived from physical dimensions — rough comparison only.

```text
radial thickness = (OD - ID) / 2
A_e,approx       = radial thickness × height     (physical cross-section)
l_e,approx       = π × mean diameter
volume,approx    = π/4 × (OD² - ID²) × height
```

| Part | Radial thickness | Approx A_e | Approx path l_e | Approx volume | A_e / l_e relative to LO1234 |
|---|---:|---:|---:|---:|---:|
| LO1230 | 4 mm | 24 mm² | 44.0 mm | 1056 mm³ | 0.686 |
| LO1234 | 5 mm | 50 mm² | 62.8 mm | 3142 mm³ | 1.000 |
| LO1238 | 7 mm | 91 mm² | 88.0 mm | 8005 mm³ | 1.300 |

(The true IEC "effective area" is marginally smaller than this physical cross-section because flux density is higher near the inner radius, but `radial thickness × height` is the standard amateur approximation and is what every other table here uses.)

Interpretation: if LO1230 and LO1234 are the same L8 material, one LO1230 has ~0.69× the inductance-per-turn² of one LO1234, so:

```text
3 × LO1230 ≈ 2.06 × LO1234   (inductance-per-turn², same material, close stacking)
```

This matches the prior note that a 3 × LO1230 stack is broadly comparable to a 2 × LO1234 stack for inductance-per-turn.

---

## 4. Why a high-µ Mn-Zn core still works in a 4:1 UnUn (the 99%-efficiency mechanism)

This reconciles "L8 is a lossy *material* at 7 MHz" with the measured >99% efficiency.

A 4:1 UnUn barely flux-loads the core. In the Ruthroff/autotransformer arrangement the core mainly carries **magnetizing current**, and the magnetizing impedance is high. Loss appears as a parallel resistance `R_p` shunting the port, so:

```text
fractional loss ≈ Z_port / R_p          (for R_p >> Z_port)
```

A 2 × LO1234 stack is roughly 2000 nH/N²; 7 turns is ~100 µH at low frequency. Even with L8's permeability rolling off by 7 MHz, the winding still presents a kilohm-scale impedance across the 50 Ω port. Working backwards from the test:

```text
measured loss ≈ 0.6%  →  R_p ≈ 50 / 0.006 ≈ 8 kΩ  (referred to the 50 Ω side)
```

That is a believable equivalent loss resistance for this stack at 7 MHz. Absolute sanity check at 50 W: ~0.3 W dissipated. Port currents are roughly 1 A on the 50 Ω side and 0.5 A on the 200 Ω side; actual conductor currents in an autotransformer connection depend on the winding connection and load. Copper loss of ~0.1–0.2 W is plausible, with the balance in the core.

The numbers hang together, but the mechanism needs to be stated carefully:

- flux is set mainly by **volts-per-turn**, frequency, and core area;
- high permeability gives high magnetising inductance / impedance, which reduces shunt magnetising current;
- the core runs at low flux here because the voltage per turn is modest at 7 MHz with 7 turns and the chosen core area.

So the measured efficiency is plausible even though L8 is lossy as a material at HF: the core is not being driven hard in flux.

Caveat that still bites: this holds at **low flux / moderate power**. See Section 9 for scaling to full rating.

---

## 5. Approximate AL notes

```text
L = AL × N²        (AL usually in nH/N²)
```

**LO1234 (measured, community, VK1HW/VK5HW):**

```text
10 turns on one LO1234 ≈ 102.5 µH   →   AL ≈ 1000 nH/N²
six cores: ~100 µH ±15% at 10 turns  (≈ 30% spread overall)
shorthand: LO1234 AL ≈ 1000 nH/N², expect large tolerance
```

**LO1230 (estimated from L8 geometry):**

```text
LO1230 AL ≈ 0.686 × LO1234 AL ≈ 686 nH/N²    (estimate, not measured)
```

**LO1238 (do not infer from LO1234):** different material label, no reliable AL. Geometry alone would suggest ~1.3× LO1234 *if same material*, but it is not material-safe. Measure the batch.

---

## 6. NKO use summary

| Part | Practical NKO use | Notes |
|---|---|---|
| LO1230 | Small stacked experimental UnUns / compact lower-power builds | VK3TXD: 3 × LO1230 with 0.63 mm wire used ~50 W. Useful where size matters. |
| LO1234 | Common choke and small 4:1 UnUn candidate | Cheap, available, L8-labelled, good in stacks. 4 × LO1234 with RG316/RG317 used for 1:1 current baluns/chokes. |
| LO1238 | Larger 4:1 UnUn / larger choke candidate | Larger cross-section and volume. 1 × LO1238 used for compact 4:1 UnUn; 2 × LO1238 for higher margin. |

---

## 7. Prior NKO 4:1 UnUn thermal / loss tests

Method (`NKO_UnUn_Testing.md`):

```text
50 W RF from IC-7410
4:1 UnUn fed on the 50 Ω side
200 Ω dummy load on the high side
~5 minutes carrier
temperature rise measured at the core
```

| Build | Diameter / weight | Power | Time | Temp rise | Estimated efficiency |
|---|---:|---:|---:|---:|---:|
| 1 × LO1234, 7 turns | 25 mm / 15 g | 50 W | 300 s | 8.1 °C | 99.4% |
| 1 × LO1234, 6 turns | 25 mm / 15 g | 50 W | 300 s | 18.4 °C | 98.5% |
| 1 × LO1238, 6 turns | 35 mm / 38 g | 50 W | 307 s | 7.0 °C | 98.6% |
| 2 × LO1238, 7 turns | 35 mm / 76 g | 50 W | 306 s | 2.2 °C | 99.6% |

Interpretation:

- Practical thermal estimates, **not** certified ratings.
- 7-turn LO1234 clearly beat 6-turn LO1234 — turns/magnetizing impedance matter (Section 4).
- 2 × LO1238, 7T had the lowest rise / best efficiency in this set (most copper + most core mass + highest magnetizing impedance).
- **Measurement error bars are real:** backing ~0.3 W out of a temperature rise is noisy; a 0.1 W error swings efficiency by ~±0.3%. The conclusion (loss < 1%) is solid; the third significant figure is not.
- Supports treating loss/heating as a test item, not a saturation guess.

---

## 8. Flux-stress reference (revised)

The **unambiguous** physics is volts-per-turn:

```text
B_pk = V_winding / (4.44 × f × N_winding × A_e)
```

where `V` and `N` refer to the **same winding**. Saturation flux for L8 is **Bs ≈ 0.255 T** (Section 2). The 0.02 T figure used below is a deliberately conservative *working* reference — only ~8% of Bs.

### Winding convention (confirmed)

The winding is bifilar — two wires side by side, 7 passes through the core, i.e. **7 turns per wire**. As a Ruthroff 4:1: the **50 Ω input is across one 7-turn wire**; the 200 Ω side is both wires in series (**14 turns**) at twice the voltage. Volts-per-turn is the same either way (`V_200/14 = V_50/7`), so the flux-setting reference is unambiguous:

```text
V_50 = 4.44 × f × 7 × A_e × B        (voltage across the 7-turn / 50 Ω winding)
P    = V_50² / 50
```

(An earlier note used `V²/200` with 7 turns; that pairs the 200 Ω voltage with the wrong turn count, doubles the flux, and understates power by 4×. Superseded.)

### Equivalent power at the 0.02 T working reference, f = 7 MHz

Bs for L8 ≈ **0.255 T** (Section 2); 0.02 T is a deliberately conservative working reference, only ~8% of Bs.

| Core stack | A_e | V_50 @ 0.02 T | Equivalent through-power (P = V_50² / 50) |
|---|---:|---:|---:|
| 1 × LO1230 | 24 mm² | 104 V | 218 W |
| 3 × LO1230 | 72 mm² | 313 V | 1.96 kW |
| 1 × LO1234 | 50 mm² | 218 V | 947 W |
| 2 × LO1234 | 100 mm² | 435 V | 3.79 kW |
| 1 × LO1238 | 91 mm² | 396 V | 3.14 kW |
| 2 × LO1238 | 182 mm² | 792 V | 12.5 kW |

### What this means

- This is **not** a power-rating table. It states the through-power that drives the core to a chosen 0.02 T flux reference.
- Huge headroom vs Bs = 0.255 T. Worked example, 1 × LO1234 at 100 W: V_50 = √(100 × 50) = 70.7 V across 7 turns → **B ≈ 0.0065 T**, about 2.5% of saturation.
- **Conclusion:** at any realistic power the flux is a small fraction of saturation. Saturation is essentially never the HF limit for these cores. **Loss/heating is.**

---

## 9. Scaling a tested UnUn to full rating

The 50 W tests do not extrapolate simply to, say, 600 W:

- **Copper loss** scales approximately with power (×12 from 50 → 600 W), assuming the same impedance and current distribution.
- **Core loss** may rise more than linearly with transmitter power. If core loss follows a Steinmetz-style relationship with flux density, and flux rises with voltage, then a 12× power increase could plausibly produce roughly **12–25×** core-loss increase, depending on material, frequency, flux level, winding, and temperature. Treat this as a caution, not a precise prediction.
- **Thermal behaviour is the real risk.** Ferrite loss can rise with temperature, so a long key-down at high power can creep upward and, in a bad case, run away. Negligible at ~0.3 W loss; something to respect at several watts in a stacked pair with limited airflow.
- **Test, don't extrapolate:** key down at the intended power for the real duty cycle and watch whether the **core** temperature plateaus (good) or keeps creeping. Single-band 40 m is the easier case; broadband HF is where material rolloff and loss make known RF ferrites such as Ni-Zn 43/61 the safer default.

---

## 10. Prior NKO choke impedance notes

Practical project notes, not manufacturer specs. Approximate common-mode |Z| at band centres:

| Choke build | 160 m | 80 m | 40 m | 30 m | 20 m | 17 m | 15 m | 10 m |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 4 × LO1234, 7T, spacer | 2.9 kΩ | 4.9 kΩ | 5.2 kΩ | 4.0 kΩ | 3.0 kΩ | 2.4 kΩ | 2.2 kΩ | 2.0 kΩ |
| 4 × LO1234, 7T, no spacer | 2.9 kΩ | 4.9 kΩ | 4.8 kΩ | 3.6 kΩ | 2.7 kΩ | 2.2 kΩ | 2.0 kΩ | 1.8 kΩ |
| 2 × LO1238, 8T, spacer | 2.3 kΩ | 3.7 kΩ | 4.7 kΩ | 5.1 kΩ | 4.7 kΩ | 4.1 kΩ | 3.3 kΩ | 3.3 kΩ |
| 2 × LO1238, 9T, spacer | 3.0 kΩ | 5.1 kΩ | 6.4 kΩ | 5.9 kΩ | 4.8 kΩ | 3.9 kΩ | 3.2 kΩ | 3.1 kΩ |

Interpretation:

- More turns usually raise low-band |Z| but lower self-resonance and can hurt upper HF.
- Spacing / winding geometry improves upper HF by reducing capacitance.
- Judge a choke by common-mode impedance and thermal behaviour, not turn count.
- For the NKO lower choke: define the end of the intentional coax-shield radiator and suppress common-mode current below the choke.

---

## 11. Loss notes

### UnUn / transformer loss sources

ferrite core loss · copper resistance · skin/proximity effects · dielectric/leakage · mismatch-driven high voltage or circulating current · high duty cycle · poor layout / excess inter-winding capacitance.

Well-made small Jaycar-core UnUns can be efficient at 50 W carrier into 200 Ω (Section 7) **because** they run the core at low flux (Section 4). This does not certify them for high power, continuous/digital carriers, or all mismatch conditions (Section 9).

### Choke loss

A 1:1 current balun is different from a 4:1 transformer: wanted differential current largely cancels magnetically, and the ferrite mainly sees **common-mode** current.

> Choke heating is set by common-mode current/voltage at the choke location, **not** directly by transmitter power.

For the NKO, common-mode current **above** the lower choke is intentional; the choke stops it continuing down the feedline.

### Saturation vs the real HF limit

At HF the practical limit is rarely classic saturation (Section 8). Ask instead: How hot does the core get? Does SWR/impedance shift as it warms? Is the lowest band most stressful? Does mismatch create high V or I? SSB-only or carrier/digital? Enclosed without airflow? Turns/spacing/insulation adequate?

> Discuss RF flux stress and thermal behaviour. Do not claim a specific "saturation wattage" from a bare flux-density calculation.

---

## 12. Practical comparison

**LO1230** — very small; good in 3-core stacks (~2 × LO1234 equiv. for L/turn²); ~50 W practical. Limits: small thermal mass, small window, not for high power, no full RF data.

**LO1234** — cheap, available, L8, good for compact chokes/UnUns; AL ~1000 nH/N². Limits: smaller thermal mass than LO1238; loss/heat depend heavily on turns and layout; treat single-core builds cautiously until thermally tested; significant material tolerance.

**LO1238** — physically larger; bigger cross-section/volume; good 4:1 UnUn candidate; 2-core stack gives the best thermal/flux margin tested. Limits: material label/spec ambiguity; L15 not characterised from retail data; do not assume Fair-Rite 43/61/15 equivalence; longer magnetic path means a single LO1238 is not automatically more efficient than a good stack of smaller L8 cores.

---

## 13. Recommended AI behaviour when using this file

1. Use the dimensions and material labels above.
2. Use the L8 constants (Section 2) but respect tolerance and confidence labels; flag LO1238/L15 material uncertainty.
3. Do **not** invent L15 permeability/loss/Curie/power figures, or upgrade L8's Medium-confidence rows to fact.
4. Treat flux-stress numbers as sanity checks, not ratings. The flux-setting winding is the 7-turn / 50 Ω wire, so use `V_50 / 7` for volts-per-turn and `P = V_50² / 50` (Section 8).
5. Use the thermal-test figures (Section 7) for practical loss discussion, with error bars.
6. Distinguish: 4:1 UnUn loss · 1:1 choke common-mode dissipation · saturation/flux stress · copper/voltage stress.
7. Prefer cautious power language: "experimental," "thermally tested at…," "sensible SSB candidate," "not a certified rating."
8. When in doubt, recommend measuring: AL · VNA impedance/S-parameters · temperature rise at the intended duty cycle · lowest-band behaviour · in-situ on the real antenna.

---

## 14. External references

- Jaycar *FERRITES* reference data sheet (L8/J70/M7/S1H constants), mirrored: https://soaraperformance.com/wp-content/uploads/2017/01/Magnetic-materials.pdf
- Jaycar LO1230: https://www.jaycar.com.au/l8-18x10x6mm-toroid-or-ring-core-pack-of-6/p/LO1230
- Jaycar LO1234: https://www.jaycar.com.au/l8-25x15x10mm-toroid-or-ring-cores-pack-of-4/p/LO1234
- Jaycar LO1238: https://www.jaycar.com.au/l15-35x21x13mm-toroid-or-ring-cores-pack-of-2/p/LO1238
- VK5HW / VK1HW common-mode choke (LO1234 AL, tolerance): https://sites.google.com/view/vk1hw/homebrew/common-mode-choke
- Marxy blog (VK3TXD toroid notes): https://blog.marxy.org/2024/05/constructive-feedback-on-my-naive-end.html
- EEVblog Jaycar L15 discussion: https://www.eevblog.com/forum/rf-microwave/jaycar-l15-toroid/
- Google Groups L15 identity (VK1OD µi ≈ 1100): https://groups.google.com/g/rec.radio.amateur.antenna/c/MdJ2qEMVW54

---

## 15. Bottom-line summary

- LO1230 and LO1234 are **L8 Mn-Zn** toroids; published L8 constants now captured: **µi ≈ 1500, Bs ≈ 0.255 T, Br ≈ 0.12 T, loss factor spec'd only to 0.3 MHz.**
- LO1238 is sold as **L15 35 × 21 × 13 mm**; no published material curve, community µi ≈ 1100 — measure the batch.
- LO1234 community AL ≈ 1000 nH/N² with ~30% spread; LO1230 ≈ 686 nH/N² by geometry; LO1238 AL must be measured.
- L8 is Mn-Zn and LF/suppression-oriented, not the Ni-Zn 43/61 normally used at HF. LO1238/L15 appears to be a high-permeability suppression ferrite, but its full material data is not publicly characterised; measure the batch.
- These cores can nonetheless test efficient in a 4:1 UnUn because the **volts-per-turn and resulting flux are low**, while high permeability helps magnetising impedance. Do not read that as proof that the material itself is low-loss at 7 MHz.
- Flux at realistic power is a small fraction of Bs (1 × LO1234 at 100 W ≈ 0.0065 T vs Bs 0.255 T) — **saturation is not the HF limit; heating is.**
- Rate these builds by measured impedance, temperature rise under real duty cycle, RF flux stress, and construction quality — not by vague "saturation wattage."
