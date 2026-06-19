# NKO Transformer Flux Stress Notes

Saturation is often raised as a possibility for Amateur Radio UnUn and balun devices. Indeed, when I describe the NKO antenna, it is usual to get at least one person asking about saturation.

## Purpose

These notes address a question about the ferrite transformer used in the NKO antenna system:

> Will the apex 4:1 UnUn core saturate?

For HF RF transformers, this is usually the wrong first question.

At 7 MHz, with a sensible number of turns, classic low-frequency-style magnetic saturation is usually **not** the practical limit. The more useful engineering question is:

> What is the RF **flux stress** in the core, and is the transformer likely to heat, become lossy, or suffer voltage, copper, insulation, or mismatch stress under real operating conditions?

This file therefore discusses **RF flux stress**, not claimed "saturation power ratings".

The practical message is:

> In normal NKO HF use, classic magnetic saturation is unlikely to be the first limiting mechanism. Heating, mismatch, RF voltage, winding layout, ferrite RF loss, duty cycle, and construction quality are the real engineering limits.

The goal is to give technically-minded amateurs a way to sanity-check transformer builds without turning a theoretical saturation calculation into a misleading power rating.

---

## Scope

The calculations below are for an **apex 4:1 UnUn / autotransformer style transformer** used in the NKO antenna system.

They are not a final power rating for any build.

They are a flux-voltage sanity check only.

Practical power handling still depends on:

- ferrite material
- core size and number of stacked cores
- winding style
- copper loss
- skin and proximity effects
- dielectric / insulation voltage stress
- mismatch
- duty cycle
- carrier vs SSB use
- airflow and enclosure heating
- water ingress and construction quality
- real antenna impedance on each band
- thermal testing

---

## Important distinction: saturation vs flux stress

Ferrite cores do have a magnetic saturation region, but at HF the core will generally become lossy and heat long before a simple transformer formula predicts classic magnetic saturation.

Saturation happens at very high power, many kilowatts, but before then "flux stress" is a consideration.

So a calculation that says "this core would not saturate until many kilowatts" should **not** be read as:

> This transformer is safe for many kilowatts.

It should be read as:

> Classic magnetic saturation is not the limiting mechanism in this case. Heating, ferrite RF loss, winding loss, mismatch, and voltage stress are the practical limits.

For this reason, these notes use the phrase **RF flux stress** rather than **saturation power**.

---

## 7-turn bifilar convention

For a standard bifilar Ruthroff-style 4:1 UnUn used in this NKO context:

```text
two wires side by side (bifilar)
7 passes through the core
= 7 turns per wire
```

In that arrangement:

| Part of transformer | Turns involved | Voltage relationship |
|---|---:|---|
| 50 ohm input side | one 7-turn wire | lower voltage |
| 200 ohm high side | two 7-turn wires in series = 14 turns | twice the voltage |

The important point is that **volts per turn are the same either way**:

```text
V50 / 7 = V200 / 14
```

Flux calculations must use voltage and turns from the **same winding section**.

The calculation may be done either way:

```text
V50  = voltage across the 7-turn / 50 ohm side
P    = V50² / 50
```

or equivalently:

```text
V200 = 2 × V50
N200 = 14 turns
P    = V200² / 200
```

Both methods give the same flux, provided the voltage and turn count belong to the same winding section.

---

## Why the table uses the 50 ohm winding

The NKO apex transformer is normally thought of as a 4:1 impedance transformer.

A nominal 4:1 impedance transformation means:

```text
50 ohms on the transceiver/coax side
appears as about
200 ohms on the high-impedance antenna side
```

The transceiver is still a 50 ohm source.

The **200 ohm figure is not the transmitter output impedance**.

It is the approximate high-side impedance associated with an ideal 4:1 transformation.

This matters because ferrite flux stress is related to **voltage per turn**, not directly to the label "50 ohm radio" or "200 ohm antenna side".

For the same through-power:

```text
P = V² / R
```

At 100 W:

| Point in system | Nominal resistance | RMS voltage | Turns in 7T bifilar model |
|---|---:|---:|---:|
| Transceiver / coax side | 50 ohms | 70.7 V RMS | 7 turns |
| High side of 4:1 transformer | 200 ohms | 141.4 V RMS | 14 turns |

So the high side has about **twice the voltage**, but also **twice the turns**.

That means the volts-per-turn are the same:

```text
70.7 / 7 = 141.4 / 14
```

For clarity and repeatability, the flux-stress table uses:

```text
V50 across the 7-turn winding
P = V50² / 50
```

This does **not** mean the 200 ohm side is ignored. It means the flux-setting section is handled consistently.

---

## Why this is conservative

The method used here is conservative in several ways:

1. It uses **0.02 T / 200 gauss** as a practical RF flux-stress reference, not a high saturation figure such as 0.255 T, 0.3 T, or 0.35 T.
2. It keeps voltage and turns from the same transformer section.
3. It treats stacked cores as increased cross-sectional area, which reduces calculated flux stress, but it still does not claim a certified power rating.
4. It keeps the conclusion focused on **thermal testing and practical construction**, not theoretical saturation limits.

For example, at 100 W:

```text
50 ohm side voltage ≈ 70.7 V RMS across 7 turns
200 ohm high-side voltage ≈ 141.4 V RMS across 14 turns
```

For one LO1234 core, 7 turns, 7 MHz, the 0.02 T flux-stress reference voltage across the 7-turn 50 ohm winding is about:

```text
218 V RMS
```

So a nominal 100 W case corresponds to:

```text
70.7 / 217.6 ≈ 0.325
```

Flux stress scales approximately with voltage, so:

```text
0.325 × 0.02 T ≈ 0.0065 T
```

That is about:

```text
0.0065 T = 65 gauss
```

This is below the already conservative 0.02 T reference.

This does **not** prove that a one-core LO1234 transformer is safe at any particular power. It does show that, in the nominal matched case, classic magnetic saturation is not the obvious limiting mechanism.

The real limit remains heating, mismatch, winding layout, voltage stress, duty cycle, and thermal testing.

---

## Formula used

For a sinusoidal waveform, the usual transformer voltage/flux relationship is:

```text
V_RMS = 4.44 × f × N × A_e × B
```

Where:

| Symbol | Meaning |
|---|---|
| `V_RMS` | RMS voltage across the winding section being analysed |
| `f` | frequency in hertz |
| `N` | number of turns in that same winding section |
| `A_e` | effective magnetic cross-sectional area of the core in square metres |
| `B` | peak flux density in tesla |

Rearranged:

```text
B = V_RMS / (4.44 × f × N × A_e)
```

This is the same basic transformer equation commonly used at power frequencies. It is useful here as a **sanity check**, but it is not a complete RF power-rating method.

For these estimates:

```text
f = 7 MHz
N = 7 turns on the 50 ohm winding
B = 0.02 T
```

The value **0.02 T**, or **200 gauss**, is used as a rough RF flux-stress reference point.

It is **not** a claimed saturation point.

It is a deliberately conservative "this is now a meaningful RF flux level" figure used to make the numbers more realistic than a true saturation calculation.

---

## Why not use a saturation flux value?

If we use a high flux value such as 0.255 T, 0.3 T, or 0.35 T, the calculated voltage and power numbers become very large.

For example, for a small core with 7 turns at 7 MHz, a true saturation-style calculation can imply very high powers. That may be arithmetically consistent, but it is practically misleading.

At HF, ferrite material losses rise, the core heats, and the transformer may fail thermally or electrically long before such a magnetic saturation point is approached.

So the numbers below deliberately use **0.02 T flux stress**, not a saturation figure.

---

## Material notes: LO1234 / LO1230 / LO1238

For the Jaycar/Electus LO123x cores used in NKO experiments:

- **LO1230** and **LO1234** are L8-labelled Mn-Zn ferrite.
- Published L8 material data gives saturation flux density around:

```text
Bs ≈ 2550 gauss ≈ 0.255 T
```

- The 0.02 T reference is therefore:

```text
0.02 / 0.255 ≈ 0.078
```

or about:

```text
8% of the L8 saturation flux density
```

That does **not** mean the transformer is safe at the equivalent powers shown in the table. It means the table is a conservative RF flux-stress sanity check.

For **LO1238**, the physical size is normally treated as:

```text
35 mm OD × 21 mm ID × 13 mm high
```

but the L15 material data is less well characterised from public retail information. Treat LO1238 calculations as geometry-based comparisons and verify the actual build by measurement and thermal testing.

Important distinction:

> High permeability does not directly reduce flux. Flux is set mainly by volts-per-turn, frequency, and core area. High permeability helps by increasing magnetising inductance and magnetising impedance, reducing shunt magnetising current.

This is why a high-permeability Mn-Zn suppression-style ferrite can still test efficiently in a lightly flux-loaded 4:1 UnUn, while still not being a general-purpose low-loss HF power ferrite in every application.

---

## Worked example: 1 × LO1234, 7 turns, 7 MHz

Approximate dimensions for one LO1234 core are taken as:

```text
OD = 25 mm
ID = 15 mm
Height = 10 mm
```

Approximate radial thickness:

```text
(OD - ID) / 2 = (25 - 15) / 2 = 5 mm
```

Approximate magnetic cross-sectional area:

```text
A_e ≈ radial thickness × height
A_e ≈ 5 mm × 10 mm
A_e ≈ 50 mm²
```

Convert to square metres:

```text
50 mm² = 50 × 10^-6 m²
       = 0.000050 m²
```

Use the transformer formula:

```text
V_RMS = 4.44 × f × N × A_e × B
```

Substitute, using the 7-turn 50 ohm winding:

```text
V50 = 4.44 × 7,000,000 × 7 × 0.000050 × 0.02
```

Step by step:

```text
4.44 × 7,000,000 = 31,080,000

31,080,000 × 7 = 217,560,000

217,560,000 × 0.000050 = 10,878

10,878 × 0.02 = 217.56 V RMS
```

So for one LO1234 core, 7 turns, 7 MHz, at a flux stress of 0.02 T:

```text
V50 ≈ 218 V RMS
```

If we ask what equivalent through-power this voltage would represent into the nominal 50 ohm side:

```text
P = V50² / 50
```

```text
P = 217.56² / 50
P ≈ 947 W
```

This does **not** mean that one LO1234 core is a 947 W rated transformer.

It means that, under these assumptions, about 947 W of equivalent through-power would correspond to about 0.02 T flux stress in the 7-turn 50 ohm winding.

The same result can be seen from the 200 ohm side when 14 turns are used:

```text
V200 = 2 × 217.56
V200 ≈ 435 V RMS
N200 = 14 turns
P = V200² / 200
P ≈ 947 W
```

The real transformer may be limited below this by heating, mismatch, duty cycle, winding loss, insulation stress, and construction.

---

## Worked example: 100 W from a 50 ohm transmitter

A 100 W transmitter working into a matched 50 ohm system produces:

```text
V50 = sqrt(P × R)
V50 = sqrt(100 × 50)
V50 = 70.7 V RMS
```

In an ideal 4:1 impedance transformer, the high side is about 200 ohms.

For the same 100 W:

```text
V200 = sqrt(100 × 200)
V200 = 141.4 V RMS
```

In the bifilar Ruthroff interpretation:

```text
V50  = 70.7 V across 7 turns
V200 = 141.4 V across 14 turns
```

The volts-per-turn are the same:

```text
70.7 / 7 = 141.4 / 14
```

Compare the 50 ohm side voltage with the one-core LO1234 0.02 T reference voltage:

```text
70.7 / 217.6 ≈ 0.325
```

Therefore the estimated flux stress is:

```text
0.325 × 0.02 T ≈ 0.0065 T
```

Or approximately:

```text
0.0065 T = 65 gauss
```

Compared with L8 saturation flux density:

```text
0.0065 / 0.255 ≈ 0.025
```

So at nominal 100 W and 7 MHz:

```text
B ≈ 2.5% of L8 Bs
```

This is below the deliberately conservative 0.02 T reference.

Again, this is a flux-stress sanity check only. It is not a complete power rating.

---

## What happens under mismatch?

The calculations above assume a nominal matched transformation.

Real antenna impedance can vary by band, height, wire geometry, ground, nearby objects, weather, vertical coax-shield length, choke placement, and installation details.

For a given power, higher load resistance means higher voltage:

| Antenna-side impedance | RMS voltage at 100 W |
|---:|---:|
| 50 ohms | 70.7 V |
| 100 ohms | 100 V |
| 200 ohms | 141 V |
| 400 ohms | 200 V |
| 800 ohms | 283 V |

This table is useful as a voltage warning, but the voltage must be paired with the matching winding turn count.

For a standard 7-turn bifilar 4:1:

```text
200 ohm high-side voltage belongs with 14 turns
50 ohm low-side voltage belongs with 7 turns
```

A tuner or mismatch can increase the voltage appearing across the transformer.

For a given voltage increase, flux stress increases in direct proportion:

| Voltage increase | Flux increase | Approx power ratio if impedance unchanged |
|---:|---:|---:|
| 1× | 1× | 1× |
| 1.5× | 1.5× | 2.25× |
| 2× | 2× | 4× |
| 3× | 3× | 9× |

This is why mismatch matters.

A high antenna-side impedance can increase winding voltage and flux stress even though the transceiver is still designed for 50 ohms.

This is also why thermal testing on the real antenna, on the intended bands, matters more than a single table calculation.

---

## Estimated flux-stress table

Assumptions:

- Standard bifilar Ruthroff-style 4:1 UnUn
- 7 turns per wire
- 50 ohm side is one 7-turn winding
- 200 ohm side is both windings in series, 14 turns
- Frequency: **7 MHz**
- Reference flux stress: **0.02 T / 200 gauss**
- Equivalent power uses:

```text
P = V50² / 50
```

- Core areas are approximate geometry estimates
- Stacked cores are assumed to double the effective cross-sectional area
- This is a flux-stress comparison, not a certified power rating

| Ferrite core(s) | Turns | Approx core area | V50 at 0.02 T flux stress | Equivalent through-power at 0.02 T flux stress | Comment |
|---|---:|---:|---:|---:|---|
| 1 × LO1230 | 7 | 24 mm² | 104 V RMS | 218 W | Small experimental core; limited thermal mass |
| 3 × LO1230 | 7 | 72 mm² | 313 V RMS | 1.96 kW | Compact stack; useful comparison to 2 × LO1234 class |
| 1 × LO1234 | 7 | 50 mm² | 218 V RMS | 947 W | 100 W nominal flux stress is low; still thermally test |
| 2 × LO1234 | 7 | 100 mm² | 435 V RMS | 3.79 kW | Much better voltage and thermal margin than one core |
| 1 × LO1238 | 7 | 91 mm² | 396 V RMS | 3.14 kW | Larger single core; material less characterised than L8 |
| 2 × LO1238 | 7 | 182 mm² | 792 V RMS | 12.5 kW | High theoretical flux margin; heating still decides |
| 1 × FT140-43 | 7 | ~85 mm² | 370 V RMS | 2.74 kW | Approximate #43 comparison; not same material as L8/L15 |
| 2 × FT140-43 | 7 | ~170 mm² | 740 V RMS | 10.95 kW | Strong flux-stress margin; practical rating still thermal |

---

## How to read the table

The table does **not** say:

> A single LO1234 is safe at 947 W.

It says:

> About 947 W of equivalent through-power would correspond to about 0.02 T flux stress in the 7-turn 50 ohm winding.

The table also does **not** say:

> Two LO1238 cores are a 12.5 kW transformer.

It says:

> A two-core LO1238 stack has much more cross-sectional area, so for the same voltage and turns it has lower flux stress.

In practice, a transformer may fail or become unsuitable because of:

- ferrite heating
- copper heating
- poor winding layout
- high RF voltage between turns
- mismatch causing high voltage or circulating current
- core material losses at the operating frequency
- continuous carrier use
- inadequate ventilation
- water ingress or enclosure heating

---

## Why stacked cores help

Stacking two identical toroids approximately doubles the magnetic cross-sectional area.

From the formula:

```text
V_RMS = 4.44 × f × N × A_e × B
```

If `A_e` doubles, then for the same frequency, turns, and flux density, the voltage at the same flux stress also doubles.

Because power into a fixed resistance is:

```text
P = V² / R
```

Doubling the voltage corresponds to four times the calculated equivalent power at the same flux stress.

This is why the table shows a large increase when moving from one core to two cores.

However, this does not mean the practical RF power rating automatically increases by four times. Thermal behaviour, loss, voltage stress, and winding details still matter.

---

## Why more turns help

From the same formula:

```text
V_RMS = 4.44 × f × N × A_e × B
```

For a given voltage, more turns reduce flux stress.

That is useful, but there is a trade-off.

Too many turns can introduce:

- extra winding capacitance
- lower self-resonant frequency
- poorer high-band performance
- more copper length and loss
- less predictable transformer behaviour on upper HF bands

For the NKO 80 m class transformer, 6 or 7 turns has been used as a practical compromise. A 7-turn table is used here because it is a conservative and repeatable reference.

---

## Why frequency matters

Flux stress is inversely related to frequency for a given voltage, number of turns, and core area.

Rearranging the formula:

```text
B = V_RMS / (4.44 × f × N × A_e)
```

So at lower frequency, the same voltage causes higher flux stress.

For example, all else equal:

- flux stress at 3.5 MHz is about twice the flux stress at 7 MHz
- flux stress at 14 MHz is about half the flux stress at 7 MHz
- flux stress at 28 MHz is about one quarter the flux stress at 7 MHz

This means an 80 m transformer deserves more caution than a 40 m-only transformer, especially under mismatch or high-duty operation.

---

## 80 m check: 1 × LO1234 at 100 W

At 7 MHz, one LO1234 at 100 W nominal gives:

```text
B ≈ 0.0065 T
```

At 3.5 MHz, all else equal:

```text
B ≈ 0.013 T
```

Compared with L8 saturation flux density:

```text
0.013 / 0.255 ≈ 0.051
```

So even on 80 m, classic saturation is not the obvious limit at nominal 100 W.

Heating, mismatch, duty cycle, and construction remain the real concerns.

---

## Loss and heating notes

### Flux stress is not the same as loss

The formula above tells us magnetic flux density.

It does not directly tell us how hot the core will get.

At HF, ferrite heating depends on:

- material loss at frequency
- flux level
- magnetising current
- equivalent parallel loss resistance
- winding and layout
- copper loss
- voltage stress
- duty cycle
- enclosure temperature

### High permeability does not directly reduce flux

Flux is set mainly by:

```text
volts per turn
frequency
core area
```

High permeability helps by increasing magnetising inductance and magnetising impedance, reducing shunt current.

So the useful explanation is:

> The core runs at low flux because the volts-per-turn are modest at 7 MHz with 7 turns and the chosen core area. High permeability helps magnetising impedance, but flux itself is set by voltage, frequency, turns, and core area.

### Thermal tests matter most

NKO tests at 50 W carrier into a 200 ohm dummy load showed low temperature rise and high estimated efficiency for several LO123x builds. Those tests are valuable because they examine the real practical issue: loss and heating.

But do not extrapolate 50 W tests directly to high power.

Copper loss rises approximately with power. Core loss may rise more than linearly with power depending on material, flux, frequency, and temperature. A build that is fine at 50 W may still need proper thermal verification at 100 W, 400 W, or higher.

---

## NKO-specific interpretation

For the NKO apex transformer, the question is not simply:

> Will the core saturate?

The better questions are:

1. What is the real antenna impedance on each band?
2. What voltage appears across the relevant winding section?
3. What current flows in the winding?
4. How much heat is produced in the ferrite and copper?
5. Does the transformer remain stable and cool during realistic operation?
6. Does the SWR or received/transmitted behaviour change as the transformer warms?
7. Is the build suitable for the intended duty cycle?

The NKO does not require uncontrolled or mysterious ferrite behaviour. The transformer is simply an RF power component and should be treated as such.

---

## Practical wording for the NKO project

Recommended wording:

> The NKO apex UnUn should be assessed by RF flux stress and thermal behaviour, not by scary saturation claims. In the 7-turn bifilar Ruthroff model, the 50 ohm side is one 7-turn winding and the 200 ohm side is 14 turns at twice the voltage, so volts-per-turn are the same either way. At nominal 100 W and 7 MHz, one LO1234 is around 0.0065 T, far below the L8 saturation flux density. Classic saturation is therefore unlikely to be the limiting mechanism. Practical suitability must be established by thermal testing, mismatch behaviour, voltage stress, winding layout, ferrite loss, duty cycle, and construction quality.

Also recommended:

> The 200 ohm figure is the nominal high side of a 4:1 transformation from a 50 ohm transmitter system. It is not saying the transmitter directly drives a 200 ohm load. If the 200 ohm side is used in a flux calculation, it must be paired with the 14-turn high-side winding in the standard 7-turn bifilar Ruthroff connection.

Avoid wording such as:

> This core saturates at 72 kW.

That number may follow from a simple saturation-flux calculation, but it is misleading and invites the wrong argument.

Better wording:

> The calculated flux-stress margin is large; practical suitability must be established by thermal testing and construction quality.

---

## Suggested practical ratings language

These are cautious descriptions, not certified ratings:

| Build | Sensible wording |
|---|---|
| 1 × LO1230, 7T bifilar | Small experimental / low-power only unless thermally tested |
| 3 × LO1230, 7T bifilar | Compact low-to-medium power experimental build; test thermally |
| 1 × LO1234, 7T bifilar | Credible 100 W SSB candidate if thermally verified |
| 2 × LO1234, 7T bifilar | Stronger 100 W SSB candidate; better thermal and flux margin |
| 1 × LO1238, 7T bifilar | Credible 100 W SSB candidate; material data less certain |
| 2 × LO1238, 7T bifilar | Sensible higher-power SSB candidate; thermal test still required |
| 1 × FT140-43, 7T bifilar | Similar physical class to LO1238 but known #43 material; test build |
| 2 × FT140-43, 7T bifilar | Stronger higher-power candidate; still not a certified rating |

The safest public position is:

> Flux-stress calculations show that classic saturation is unlikely to be the first limiting mechanism. Practical power handling must be established by construction quality and thermal testing.

---

## Suggested thermal test

A useful amateur-level test is:

1. Assemble the transformer in its intended enclosure.
2. Connect it to a representative load or antenna.
3. Measure initial core/enclosure temperature.
4. Transmit at the intended power level and duty cycle.
5. Measure temperature rise at intervals.
6. Watch whether temperature plateaus or continues creeping upward.
7. Check whether SWR, tuning, or RF behaviour changes as it warms.
8. Repeat on the lowest intended band, because flux stress is higher at lower frequency.
9. Inspect for dielectric stress, arcing, softened insulation, moisture, mechanical movement, or smell of hot material.

For SSB service, a test that includes a realistic transmit/receive cycle is more representative than a long continuous carrier. However, a short carrier test can be useful as a worst-case screen if kept within safe limits.

---

## Summary

- Do not describe the NKO apex transformer limit primarily as **saturation**.
- Describe it as **RF flux stress plus thermal and voltage limits**.
- A true saturation calculation at HF gives unrealistically large power numbers and should not be used as a power rating.
- A 0.02 T flux-stress reference gives a more useful comparison point.
- The 7-turn bifilar model uses the 7-turn / 50 ohm winding for flux calculation.
- The 200 ohm side is 14 turns at twice the voltage.
- At 100 W and 7 MHz, one LO1234 is about **0.0065 T**, roughly **2.5% of L8 Bs**.
- At 100 W and 3.5 MHz, one LO1234 is about **0.013 T**, roughly **5% of L8 Bs**.
- Classic magnetic saturation is therefore not the likely HF limit.
- The real limits are heating, mismatch, duty cycle, winding layout, ferrite RF loss, insulation, and construction quality.
- Stacked cores reduce flux stress and improve thermal margin.
- More turns reduce flux stress but can compromise high-band behaviour.
- Practical suitability must be confirmed by thermal testing in the intended operating conditions.

The core message:

> At HF, with a 7-turn bifilar Ruthroff-style 4:1 UnUn, saturation is not the scary part. Heating and practical RF construction are.
