# HF Propagation Primer — Ionosphere, Fading, Modes, TEP, TIDs, and Practical Antenna Readability

**Purpose:** This primer builds a careful, source-checked explanation of the HF propagation topics raised in the conversation: D/E/F regions, daytime and night-time behaviour, absorption, gray-line/terminator propagation, solar cycles and space weather, launch angle, ducted and chordal modes, multipath, QSB, ordinary and extraordinary waves, Faraday rotation, practical reciprocity, non-reciprocal QSB, TIDs, sporadic E, TEP/aTEP/eTEP, tropospheric ducting, external radio noise, and how all of this can affect real SSB readability and antenna comparisons such as NKO field reports.

**Source policy:** Government, standards, university, and peer-reviewed sources are used as the backbone. Amateur-radio sources are intentionally not used as primary evidence. Field reports from NKO testers are treated as observations and hypotheses, not as formal proof.

**Working style:** This document uses plain radio language first, then adds the physics. Where a point is uncertain or path-dependent, it says so.

**Copyright and reuse:** © 2026 Richard Holmes (VK3TXD). You may copy, share, quote, adapt, and redistribute this document freely, provided attribution is retained. Suggested attribution: “HF Propagation Primer, Richard Holmes VK3TXD, NKO / New Kallista OCF project.” No warranty is given; verify anything important against current measurements and official data.

---


## Preface and Introduction

[Previous](#index) | [Home / Index](#index) | [Next](#1-executive-summary)

This primer can be read as a reference, but it can also be used as the backbone of a club talk. A useful way to begin such a talk is not with equations or antenna claims, but with things HF operators already hear every week and often dismiss with one word: “propagation.”

A short opening quiz could be:

1. **Why does QSB happen when neither station has changed anything?**
2. **Why does a vertical antenna work with signals from horizontal antennas?**
3. **Why might an antenna improve speech copy more than the S-meter suggests?**
4. **When does reciprocity break down in practical HF operating?**
5. **When does NEC modelling not work well for understanding how well an antenna will actually work?**

Those questions lead naturally into the main theme of this document: HF readability is not controlled by antenna gain alone. The received signal is shaped by launch angle, ionospheric absorption, ordinary and extraordinary modes, polarization rotation, multipath, selective fading, TIDs, ducted and chordal paths, noise, and the receiver/listener combination.

The NKO antenna reports are included because they raise exactly these practical questions. Some reports describe better copy, cleaner audio, or the ability to hear stations that a comparison antenna did not copy well. These are useful field observations, but they are not treated here as controlled proof. They are best read as prompts for better testing and as reminders that real HF performance includes readability, fading behaviour, and received audio quality — not just modelled free-space gain.

A useful talk caveat is:

> The NKO is not claimed to beat every antenna, every time, on every path. The interesting reports are about practical copyability. The hypothesis is that the NKO may sometimes launch or receive a more useful mix of angles, current paths, and polarization components under real ionospheric conditions.

NEC-style antenna modelling remains valuable. It is excellent for checking whether an antenna idea is electrically sane: current distribution, feed impedance, pattern shape, and likely problem areas. But a clean NEC model does not include the full ionosphere, local noise, TIDs, O/X mode behaviour, Faraday rotation, passband-selective fading, listener fatigue, or the exact clutter around a real station unless those things are explicitly represented or measured. That is why modelling, measurement, and repeated A/B field reports all have different jobs.

### References for this section

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — discusses HF path mechanisms, layers, absorption, ducting, chordal modes, and antenna gain pattern as one factor among several: https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- ITU-R Recommendation P.533, “Method for the prediction of the performance of HF circuits” — treats HF circuit performance in terms of signal-to-noise, time spread, frequency spread, reliability, and propagation mechanisms, not antenna gain alone: https://www.itu.int/rec/R-REC-P.533
- Burke and Poggio, *Numerical Electromagnetics Code (NEC) — Method of Moments*, Part III User’s Guide — describes NEC antenna modelling, segmentation, sources/loads, and ground modelling options: https://www.nec2.org/other/nec2prt3.pdf

---

## Index

0. [Preface and Introduction](#preface-and-introduction)
1. [Executive summary](#1-executive-summary)
2. [What HF skywave propagation really is](#2-what-hf-skywave-propagation-really-is)
3. [The ionosphere is not a stack of hard mirrors](#3-the-ionosphere-is-not-a-stack-of-hard-mirrors)
    - [Ready reference: D/E/F1/F2 regions](#ready-reference-def1f2-regions)
4. [Why the D, E, F1, and F2 regions exist](#4-why-the-d-e-f1-and-f2-regions-exist)
5. [Absorption: how the ionosphere actually wastes RF energy](#5-absorption-how-the-ionosphere-actually-wastes-rf-energy)
6. [Day/night behaviour and the 80 m, 40 m, 20 m puzzle](#6-daynight-behaviour-and-the-80-m-40-m-20-m-puzzle)
    - [Gray-line and terminator propagation](#6a-gray-line-and-terminator-propagation)
7. [Critical frequency, foF2, MUF, LUF, OWF, and usable bands](#7-critical-frequency-fof2-muf-luf-owf-and-usable-bands)
    - [Space weather, solar cycles, and why the bands can sound dead](#7a-space-weather-solar-cycles-and-why-the-bands-can-sound-dead)
    - [The hiss we hear: atmospheric, galactic, man-made, and solar noise](#7b-the-hiss-we-hear-atmospheric-galactic-man-made-and-solar-noise)
8. [Launch angle, antenna lobes, and why the antenna does not launch one ray](#8-launch-angle-antenna-lobes-and-why-the-antenna-does-not-launch-one-ray)
    - [Ducted and chordal modes](#8a-ducted-and-chordal-modes)
    - [NEC modelling: what it can and cannot tell you about HF copy](#8b-nec-modelling-what-it-can-and-cannot-tell-you-about-hf-copy)
9. [Multipath and QSB](#9-multipath-and-qsb)
10. [Selective fading, passband damage, and why SSB can become impossible to tune](#10-selective-fading-passband-damage-and-why-ssb-can-become-impossible-to-tune)
11. [The Earth's magnetic field and why the ionosphere is direction-sensitive](#11-the-earths-magnetic-field-and-why-the-ionosphere-is-direction-sensitive)
12. [Ordinary and extraordinary waves: O-mode and X-mode](#12-ordinary-and-extraordinary-waves-o-mode-and-x-mode)
13. [Faraday rotation and practical reciprocity](#13-faraday-rotation-and-practical-reciprocity)
    - [Practical reciprocity, non-reciprocal QSB, and what operators really hear](#13a-practical-reciprocity-non-reciprocal-qsb-and-what-operators-really-hear)
14. [Travelling ionospheric disturbances, or TIDs](#14-travelling-ionospheric-disturbances-or-tids)
15. [Sporadic E](#15-sporadic-e)
16. [Transequatorial propagation: TEP, aTEP, and eTEP](#16-transequatorial-propagation-tep-atep-and-etep)
17. [Tropospheric ducting and VHF/UHF repeater openings](#17-tropospheric-ducting-and-vhfuhf-repeater-openings)
18. [VK3RHF-style multi-band repeater events: best propagation guesses](#18-vk3rhf-style-multi-band-repeater-events-best-propagation-guesses)
19. [VK4 inland Queensland geography: what it may hint at](#19-vk4-inland-queensland-geography-what-it-may-hint-at)
20. [NKO audio/readability reports: cautious propagation interpretation](#20-nko-audioreadability-reports-cautious-propagation-interpretation)
21. [Comparing antennas without fooling ourselves](#21-comparing-antennas-without-fooling-ourselves)
22. [Practical indicators to watch](#22-practical-indicators-to-watch)
23. [What is solid, what is plausible, and what still needs testing](#23-what-is-solid-what-is-plausible-and-what-still-needs-testing)
24. [Consolidated source list](#24-consolidated-source-list)
25. [Glossary](#25-glossary)

---

## 1. Executive summary

[Previous](#preface-and-introduction) | [Home / Index](#index) | [Next](#2-what-hf-skywave-propagation-really-is)

HF propagation is not a simple reflection from a neat layer. It is the changing result of radio waves passing through a moving, magnetised, partly ionised atmosphere.

A useful first picture is:

```text
Transmitter antenna launches many angles
↓
D region absorbs some energy, especially lower HF during day
↓
E/F regions bend some energy back toward Earth if frequency and angle suit
↓
The Earth's magnetic field splits the allowed propagation into O and X modes
↓
TIDs, tilts, sporadic E, equatorial effects, and changing electron density alter the path
↓
Receiver hears the sum of all surviving components
```

The key practical consequences are:

- HF signals fade because the receiver often hears several versions of the same signal arriving with different phase, delay, polarization, and strength.
- An SSB signal can be strong but unreadable if selective fading damages the speech passband.
- A receiver can sometimes feel “impossible to tune” because the RF passband itself has been phase-smeared or selectively faded, not because the operator has tuned wrongly.
- The D region mainly causes loss; the F region is the main long-distance HF bending region; the E region can produce normal E paths and sporadic E.
- Gray-line/terminator propagation is not a magic pipe along the day-night boundary. It is a short-lived set of favourable and unfavourable conditions around sunrise/sunset: D-region absorption can drop quickly while F-region ionisation may still be useful, and steep ionospheric gradients can bend, steer, or disturb paths.
- “The bands are dead” can mean several different things: the MUF is below the band, the LUF is above the band, the path is disturbed by geomagnetic activity, D-region absorption is too high, the receiving noise floor is too high, or the antenna is sampling the wrong angles/polarization for that path.
- Solar maximum can improve the upper HF bands by increasing ionisation, but it also increases the chance of flares, radio blackouts, solar proton events, geomagnetic storms, and solar radio noise.
- Ducted and chordal modes are special cases where the signal can undergo several ionospheric refractions without returning to the ground between them. They can give unexpectedly strong long paths because they avoid some ground-reflection loss and some D-region absorption.
- The hiss heard in an HF receiver is usually a mixture of atmospheric lightning noise, man-made noise, galactic noise, receiver noise, and sometimes solar radio noise. At quiet sites and higher HF, galactic noise can become more obvious, especially at night.
- The O and X waves are not separate messages. They are two natural propagation modes of the same electromagnetic field in a magnetised plasma.
- Faraday rotation can change polarization and can break simple polarization reciprocity, but it does not by itself make a perfect one-way radio path.
- Practical reciprocity is weaker than the slogan suggests. A passive antenna may be reciprocal, but HF QSOs are not usually simultaneous laboratory measurements. One station can hear deep QSB while the other hears a steady signal because the channel changes between overs, the antennas couple differently into the available modes, and local noise floors differ.
- TIDs are travelling electron-density and layer-shape disturbances, usually driven by atmospheric gravity waves or space-weather coupling. They ripple, tilt, focus, and defocus HF paths.
- TEP is especially important for north-south-ish paths crossing the geomagnetic equator. Afternoon TEP and evening TEP have different character.
- VHF/UHF repeater openings over hundreds of kilometres are often tropospheric ducting if the active input is UHF/VHF, but 10 m and 6 m can be ionospheric: sporadic E, F2, or TEP depending on timing and path.
- NEC modelling is useful for antenna currents, feed impedance, and idealised pattern shape, but it does not by itself predict ionospheric readability, QSB, local noise, or the listener’s ability to recover SSB speech.
- In antenna reports, “readability” can improve much more than the S-meter suggests, because the antenna may be sampling a cleaner mix of arrival angles and polarization components.

### References for this section

- NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere
- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Naval Postgraduate School, “Ionospheric Radiowave Propagation” — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- ITU-R Recommendation P.533, “Method for the prediction of the performance of HF circuits” — https://www.itu.int/rec/R-REC-P.533
- Burke and Poggio, *Numerical Electromagnetics Code (NEC) — Method of Moments*, Part III User’s Guide — https://www.nec2.org/other/nec2prt3.pdf

---

## 2. What HF skywave propagation really is

[Previous](#1-executive-summary) | [Home / Index](#index) | [Next](#3-the-ionosphere-is-not-a-stack-of-hard-mirrors)

HF is usually taken as 3–30 MHz. In practical radio terms, HF skywave propagation is the use of the ionosphere to bend radio waves back toward Earth. The word “reflect” is commonly used, but for most ordinary HF paths the process is not a hard mirror reflection. The wave is gradually refracted as it travels through changing electron density.

The refractive index of the ionised medium changes with height, frequency, electron density, collisions, and the Earth's magnetic field. When the frequency and launch angle are suitable, the ray gradually bends until its path turns back downward. If the frequency is too high for the path and ionosphere, the wave passes through into space. If the frequency is too low, it may be absorbed heavily before useful refraction occurs, especially in the daytime D region.

This is why HF is both powerful and unstable. It can reach beyond the horizon, across oceans, and around the world; but the path is controlled by a medium that changes with sunlight, season, solar cycle, geomagnetic state, atmospheric waves, and local geography.

A single HF circuit is not merely “transmitter to receiver.” It can contain:

- one-hop and multi-hop paths,
- E-region and F-region modes,
- mixed E/F modes,
- chordal or ducted modes,
- ordinary and extraordinary magneto-ionic modes,
- several launch angles from the same antenna,
- ground or sea reflections,
- polarization changes,
- phase and group-delay spread,
- Doppler spread,
- and fading from all of the above.

For amateur SSB, the receiver does not care which beautiful textbook path exists. It hears the vector sum of the surviving electric fields at the receiving antenna terminals. That sum determines both the S-meter reading and the actual speech readability.

### References for this section

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, especially the discussion of HF propagation modes, antenna gain pattern, frequency, state of the ionosphere, E/F modes, mixed modes, ducting, and chordal modes — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- NOAA Space Weather Prediction Center, “HF Radio Communications” — https://www.swpc.noaa.gov/impacts/hf-radio-communications
- ITU-R Recommendation P.533, official standard page — https://www.itu.int/rec/R-REC-P.533
- National Bureau of Standards / NIST legacy publication, “Ionospheric Radio Propagation” — https://nvlpubs.nist.gov/nistpubs/Legacy/circ/nbscircular462.pdf

---

## 3. The ionosphere is not a stack of hard mirrors

[Previous](#2-what-hf-skywave-propagation-really-is) | [Home / Index](#index) | [Next](#4-why-the-d-e-f1-and-f2-regions-exist)

The names D, E, F1, and F2 can make the ionosphere sound like a stack of separate transparent sheets. That is not physically accurate.

A better description is:

> The ionosphere is a continuous, changing electron-density profile with broad regions, peaks, shoulders, tilts, ripples, and patches.

NOAA NCEI explicitly says that, for convenience, the ionosphere is divided into broad regions called D, E, F, and topside, and that these may be further divided into regularly occurring layers such as F1 and F2. That wording matters. “For convenience” is a warning not to over-interpret the layer names.

Daytime may show recognisable D, E, F1, and F2 structure. At night, D largely fades, E weakens, and F1/F2 often merge into a broader F region. The F2 region remains especially important because it usually contains the highest electron density and is high enough that collision loss is much lower than in the D region.

Real ionograms also show that the ionosphere is not a perfect stack. The traces can be spread, doubled, tilted, missing, or disturbed. Virtual height is not true height: near critical frequencies, the pulse slows and the apparent height can increase sharply.

### Useful mental model

Instead of this:

```text
D: hard layer
E: hard layer
F1: hard layer
F2: hard layer
```

Think this:

```text
height ↑

F2: broad main electron-density peak, variable and often dominant for HF
F1: daytime shoulder or sub-peak, often merged at night
E: lower refracting region, sometimes thin/patchy; sporadic E can be intense
D: low absorbing region; weakly ionised but collision-heavy

Earth ↓
```

### References for this section

- NOAA NCEI, “Definition of the Ionospheric Regions (Structures)” — https://www.ngdc.noaa.gov/stp/IONO/ionostru.html
- NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere
- NOAA NCEI, “Vertical Incidence Soundings (Ionograms)” — https://www.ngdc.noaa.gov/stp/IONO/ionogram.html
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- UCAR Center for Science Education, “The Ionosphere” — https://scied.ucar.edu/learning-zone/atmosphere/ionosphere

---


### Ready reference: D/E/F1/F2 regions

This table is deliberately **order-of-magnitude only**. The ionosphere is not a fixed stack of shelves. Heights, electron densities, and neutral-particle densities vary with solar cycle, solar zenith angle, latitude, season, geomagnetic activity, tides, waves, and storms. The neutral-density column is included to show why the D region absorbs so strongly: it has far fewer free electrons than the F region, but vastly more neutral particles for electrons to collide with.

| Region | Approx. height | Main daytime behaviour | Main night-time behaviour | Approx. free-electron density, daytime | Approx. free-electron density, night | Approx. neutral particle density in height range | Main HF meaning | Variation warning |
|---|---:|---|---|---:|---:|---:|---|---|
| **D** | ~50–90 km | Forms in sunlight; strongest around local noon; absorbs HF, especially lower HF | Greatly depleted after sunset; can persist/enhance during high-energy particle events | ~10^6–10^10 m^-3 | ~10^6–10^8 m^-3, often weak/residual | ~10^20–10^22 m^-3 | Main daytime absorption region; not usually a useful HF refractor | Can jump dramatically during solar X-ray flares or polar proton events; absorption depends on both electron density and electron-neutral collision rate |
| **E** | ~90–140 km | Regular E region can refract lower HF; sporadic E is a separate, patchy, sometimes intense case | Usually much weaker; residual ionisation can remain | ~10^10–10^11 m^-3 | ~10^8–10^10 m^-3 | ~10^17–10^19 m^-3 | Can support shorter HF paths and sometimes block/hide higher F-region paths; sporadic E can support much higher frequencies | Sporadic E can be orders of magnitude stronger locally than normal E and is not well represented by the simple “regular layer” picture |
| **F1** | ~140–210 km | Daytime shoulder/sub-layer below F2; not always distinct | Usually merges into the broader F region or becomes indistinct | ~10^11–5×10^11 m^-3 | Usually not a distinct layer | ~5×10^15–10^17 m^-3 | Transitional region; can contribute to refraction but is less central than F2 | Often absent as a clean trace; F1/F2 separation depends on season, latitude, solar cycle, and time of day |
| **F2** | >~210 km; peak often ~250–400+ km | Main HF long-distance refracting region; highest electron density; height and density vary strongly | Usually persists and often becomes the only major HF-useful region | ~3×10^11–2×10^12 m^-3 | ~10^10–10^12 m^-3 | ~10^14–5×10^15 m^-3 around the main F2 heights | Main region for long-distance HF skywave; controls foF2, MUF and skip behaviour | F2 peak density may vary several-fold through the day and strongly with solar cycle, latitude, season, geomagnetic activity, and neutral winds |

**How much can these numbers move?**

- **D-region electron density** can move by orders of magnitude with altitude, local time, solar zenith angle, and solar X-ray/proton events. A quiet low-latitude D-region model gave about 10^6–10^10 m^-3, with a noon maximum near 80 km; NOAA notes that D-region absorption rises sharply when X-ray flares or solar proton precipitation increase D-region electron density.
- **F2 electron density** commonly varies by several times over a day. Ionosonde training material from NOAA/NCEI notes a typical 3–5× diurnal variation, with highest values just after noon and lowest before dawn.
- **Solar-cycle effects are large.** NOAA notes that EUV and X-ray photon flux varies by nearly a factor of ten over the 11-year solar cycle, and ionospheric density changes accordingly. Low-latitude NmF2 values can move from a few 10^11 m^-3 to around 10^12 m^-3 or more under high solar activity.
- **Neutral density is a model estimate, not a fixed measured value.** The U.S. Standard Atmosphere table is useful for order-of-magnitude neutral number densities, but above about 100 km the real thermosphere responds strongly to solar and geomagnetic activity. NRLMSIS/IRI-style models use location, date/time, solar indices, and magnetic indices because the real atmosphere/ionosphere is not fixed.
- **Latitude matters.** Equatorial, mid-latitude, auroral, and polar ionospheres behave differently. TEP, equatorial anomaly structure, polar absorption, and auroral disturbance can all make local values depart strongly from a simple global table.
- **Do not use this table for prediction.** It is a memory aid for scale and mechanism. For actual path work, use ionosonde data, foF2/MUF maps, D-region absorption products, TEC maps, and current space-weather conditions.

#### References for this ready reference

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — gives D/E/F1/F2 height ranges and notes that D, E, and F1 deplete at night, while F2 remains important: https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro%20to%20HF%20Radio.pdf
- NOAA Space Weather Prediction Center, “Ionosphere” — explains ionospheric creation by solar EUV/X-ray radiation, solar-cycle dependence, and D/E/F layering: https://www.swpc.noaa.gov/phenomena/ionosphere
- NOAA Space Weather Prediction Center, “Global D-Region Absorption Prediction Documentation” — explains D-region absorption as electron-neutral collision loss, mostly 50–90 km, and its dependence on electron density: https://www.swpc.noaa.gov/content/global-d-region-absorption-prediction-documentation
- Zhu et al., “Physical Model of D-Region Ionosphere and Preliminary Comparison with IRI and Data of MF Radar at Kunming,” *Atmosphere*, 2023 — gives D-region electron-density ranges around 10^6–10^10 m^-3 in a low/mid-latitude model/data comparison: https://www.mdpi.com/2073-4433/14/2/235
- NOAA/NCEI VIPIR training slides, “Introduction to Ionospheric Sounding” — notes strong temporal variation, F2 3–5× diurnal variation, and night-time dissipation of F1/E/D: https://data.ngdc.noaa.gov/instruments/remote-sensing/active/profilers-sounders/ionosonde/documentation/VIPIR/Ionospheric_Sounding-ASEN-5245.pdf
- Public Domain Aeronautical Software, “Tables of the U.S. Standard Atmosphere, 1976” — provides neutral number-density values versus altitude used here only for order-of-magnitude neutral-particle density: https://www.pdas.com/bigtables.html
- NASA CCMC, “NRLMSISE-00” — describes NRLMSISE-00 as an empirical global reference atmosphere model for temperatures and atmospheric-component densities: https://ccmc.gsfc.nasa.gov/models/NRLMSIS~00/
- COSPAR/URSI International Reference Ionosphere — describes IRI as an empirical standard model giving monthly-average electron density and related ionospheric parameters from inputs including solar and magnetic indices: https://irimodel.org/

## 4. Why the D, E, F1, and F2 regions exist

[Previous](#3-the-ionosphere-is-not-a-stack-of-hard-mirrors) | [Home / Index](#index) | [Next](#5-absorption-how-the-ionosphere-actually-wastes-rf-energy)

The regions exist because the atmosphere changes with height and because the Sun's radiation does not ionise every gas equally at every altitude.

Several balances are happening at once:

1. Solar EUV and X-ray radiation create ions and free electrons.
2. Atmospheric density falls with height.
3. Gas composition changes with height.
4. Ion-electron recombination rates change with chemistry and density.
5. Diffusion, winds, electric fields, and the Earth's magnetic field move plasma around.
6. Solar zenith angle changes with time of day, season, and latitude.

The result is not one smooth monotonic curve. Electron density tends to form broad maxima and shoulders.

### D region

The D region is low, roughly tens of kilometres below the E region and usually most important in daylight. It has enough free electrons to affect HF, but it is still dense enough that electron-neutral collisions are frequent. That makes it a strong absorber, especially for lower HF.

### E region

The E region is higher. Collision loss is lower than in D, and it can refract lower HF. It can also host sporadic E: thin, dense, patchy ionisation that can support surprisingly high frequencies.

### F1 region

F1 is commonly a daytime feature, often better thought of as a shoulder or sub-peak below F2 rather than a hard separate layer. At night it often merges into the broader F region.

### F2 region

F2 is the key long-distance HF region. It is high enough to have lower collision loss, often dense enough to bend HF back, and highly variable with solar cycle, time of day, season, latitude, geomagnetic activity, and neutral winds. It is also the region whose critical frequency, foF2, is watched heavily in HF prediction.

### Why F2 can be strange

F2 behaviour is not just “more sun equals more electrons.” Chemistry and transport matter. Neutral winds can move plasma along magnetic field lines. Electric fields can lift equatorial plasma. Geomagnetic activity can both enhance and depress F-region electron density depending on location, season, and storm phase. This is why the F2 region can behave differently from simple sunlight intuition.

### References for this section

- NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere
- NOAA NCEI, “Definition of the Ionospheric Regions (Structures)” — https://www.ngdc.noaa.gov/stp/IONO/ionostru.html
- NOAA NCEI metadata for ionosonde parameters and traditional height ranges — https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ngdc.stp.ionosonde%3AG00004
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- UCAR Heliophysics, “Ionosphere and Thermosphere Basics” — https://heliophysics.ucar.edu/sites/default/files/heliophysics/resources/presentations/2021-HelioSS-Zou-Ionosphere-Basics-Dynamics.pdf
- NASA, “Earth's Upper Atmosphere” — https://www.nasa.gov/image-article/earths-upper-atmosphere/

---

## 5. Absorption: how the ionosphere actually wastes RF energy

[Previous](#4-why-the-d-e-f1-and-f2-regions-exist) | [Home / Index](#index) | [Next](#6-daynight-behaviour-and-the-80-m-40-m-20-m-puzzle)

Absorption is not the ionosphere “soaking up” radio waves in a vague sense. The main HF loss mechanism in the lower ionosphere is collision loss.

The radio wave's electric field pushes free electrons back and forth. In the D region, there are many neutral molecules. The electrons collide with those neutral particles. Each collision transfers a little of the organised RF energy into random thermal motion. In plain speech: some RF energy becomes heat.

That is why the D region is troublesome. It may not have the highest electron density, but it has a high enough collision rate to waste RF energy. The lower the frequency, the worse the effect tends to be for ordinary HF paths.

NOAA's solar-flare/radio-blackout explanation says that strong solar flares produce extra ionisation in the lower, denser ionosphere, and HF waves interacting with electrons there lose energy because collisions are more frequent. NOAA's D-RAP product explicitly addresses operational D-region absorption of HF radio caused by solar X-ray flux and solar energetic particles.

### Daytime D-region absorption

In ordinary daylight, D-region absorption is one reason 80 m can be hard in the day. The wave has to pass upward through D and downward through D. On multi-hop paths, that loss repeats. Lower frequencies suffer more, so 80 m can be badly hit while 40 m remains workable.

### Solar flare absorption

During an X-ray flare, the sunlit D region can become much more ionised very quickly. The result can be a sudden HF fadeout or blackout on the sunlit side of Earth. This tends to hurt the lower HF bands first, but strong events can affect a wide part of HF.

### Polar cap absorption

Solar energetic particles can increase D-region absorption at high latitudes. This is more relevant to polar routes, aviation HF, and high-latitude circuits than ordinary mid-latitude daytime operation, but it is part of the same broad problem: more lower-ionosphere ionisation can mean more HF absorption.

### References for this section

- NOAA Space Weather Prediction Center, “Solar Flares (Radio Blackouts)” — https://www.swpc.noaa.gov/phenomena/solar-flares-radio-blackouts
- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- NOAA Space Weather Prediction Center, “HF Radio Communications” — https://www.swpc.noaa.gov/impacts/hf-radio-communications
- NOAA Space Weather Prediction Center, “Solar Radiation Storm” — https://www.swpc.noaa.gov/phenomena/solar-radiation-storm
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf

---

## 6. Day/night behaviour and the 80 m, 40 m, 20 m puzzle

[Previous](#5-absorption-how-the-ionosphere-actually-wastes-rf-energy) | [Home / Index](#index) | [Next](#6a-gray-line-and-terminator-propagation)

A useful practical question from the conversation was:

> Why can 40 m work well for local and interstate during the day when 80 m is absorbed and 20 m is dead or not yet useful?

The answer is that each band has a different balance between absorption and refraction.

### 80 m by day

80 m is low enough in frequency that daytime D-region absorption can be severe. The wave may be able to refract back, but too much energy is lost passing through the D region. On short and medium paths, especially with high-angle radiation, the signal spends enough time in the lower ionosphere for loss to dominate.

At night, D-region ionisation largely fades. With much less D absorption, 80 m improves greatly. It can then become a strong local/regional band and, under low-noise conditions, a DX band. However, night-time atmospheric noise and man-made noise can still be limiting.

### 40 m by day

40 m is high enough in frequency to suffer less D-region absorption than 80 m, but low enough that the daytime ionosphere often still supports short and medium paths. This makes 40 m an excellent daytime local/interstate band in many conditions.

When foF2 is high enough, 40 m can support high-angle NVIS-style paths. When conditions change, 40 m can go longer, especially toward evening and night.

### 20 m by day and late afternoon

20 m needs a higher maximum usable frequency than 40 m. If the F region cannot support the required oblique frequency on a given path, the signal simply passes through or lands somewhere else. This is why 20 m can seem dead even while 40 m is working well.

Later in the day, F-region structure, path geometry, and solar illumination can line up so that 20 m opens. In good solar conditions, 20 m can be excellent for long DX. But when the MUF is below the needed value, more power does not fix the missing path.

### Night-time 40 m

At night, D absorption falls. 40 m often becomes a longer-distance band. The same reduction in absorption that helps local 40 m can also allow more distant lower-angle and multi-hop paths to dominate, so the band can become more DX-like and less reliably short-local.

### The simple band logic

```text
80 m by day: often enough refraction, but too much D absorption
40 m by day: often enough refraction, tolerable D absorption
20 m by day: low absorption, but only works if the MUF supports the path
40 m at night: low D absorption, longer paths become stronger
20 m at night: may stay open in high solar conditions, but often closes earlier than lower bands
```

### References for this section

- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- NOAA Space Weather Prediction Center, “Solar Flares (Radio Blackouts)” — https://www.swpc.noaa.gov/phenomena/solar-flares-radio-blackouts
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Australian Government / Space Weather Services, “Global HF — Ionospheric Map” — https://www.sws.bom.gov.au/HF_Systems/6/5
- ITU-R Recommendation P.533 — https://www.itu.int/rec/R-REC-P.533

---


## 6A. Gray-line and terminator propagation

[Previous](#6-daynight-behaviour-and-the-80-m-40-m-20-m-puzzle) | [Home / Index](#index) | [Next](#7-critical-frequency-fof2-muf-luf-owf-and-usable-bands)

The **terminator** is the moving day-night boundary. In radio talk, **gray-line** or **grey-line propagation** usually means enhanced or unusual propagation around sunrise or sunset, often on the lower HF bands.

The common amateur explanation is:

> The D layer disappears at sunset, but the F layer remains ionised for a while, so lower HF signals suffer less absorption while still having useful skywave refraction.

That explanation is useful, but incomplete.

A better explanation is:

> Near the terminator, the ionosphere changes rapidly with distance and time. D-region absorption can collapse or build quickly, F-region ionisation can persist or decay more slowly, and sharp horizontal gradients can steer, tilt, focus, defocus, or otherwise disturb HF paths.

The Australian Space Weather Services Digital HF prediction tool treats the day/night sector at ionospheric height and marks approximate terminators because “the ability of the ionosphere to support HF circuits changes rapidly near a day/night terminator.” That is the most important practical idea.

### What changes at the terminator?

Several things happen together:

1. **D-region absorption changes quickly.**  
   The D region is strongly sunlight-dependent. Around sunset, D-region electron density and collision loss can drop quickly. Around sunrise, D-region absorption can build quickly. This strongly affects 160 m, 80 m, 60 m, 40 m, and sometimes 30 m.

2. **F-region ionisation changes more slowly.**  
   The F region is higher, thinner, and chemically different from the D region. It can remain useful after local sunset, and it can be useful before the lower absorbing region has fully built up at sunrise.

3. **There can be steep horizontal electron-density gradients.**  
   The sunlit side and dark side of the ionosphere can differ sharply. A ray entering a tilted or horizontally varying refractive region can be bent away from the path predicted by a simple great-circle, single-layer diagram.

4. **The terminator can launch or organise disturbances.**  
   Rapid heating/cooling changes around the day-night boundary can be associated with atmospheric gravity waves and travelling disturbances. These can alter height, phase, Doppler, focusing, and path stability.

5. **Noise changes too.**  
   At night, D-region absorption is reduced. That helps wanted lower-HF signals, but it can also let more distant atmospheric noise and galactic noise reach the antenna. So a band can become more open and yet not necessarily quieter.

### Does the signal actually travel along the gray line?

Sometimes the useful path may be close to the terminator. Sometimes one end of the path may be near sunrise/sunset. Sometimes the benefit may come from the signal entering or leaving the ionosphere near the terminator rather than travelling exactly along it. This distinction matters.

A peer-reviewed 7 MHz study using WSPR data describes greyline propagation as involving paths where the two stations simultaneously lie on the terminator, and also notes the practical radio usage: propagation “along the terminator” or entering/exiting the ionosphere near sunrise/sunset. That paper is useful because it treats the subject statistically rather than relying only on anecdotes, but its use of amateur beacon data means it still reflects real-world operator/network sampling biases.

So, avoid the over-simple statement:

> The signal travels down a special gray-line pipe.

Prefer:

> Around the terminator, D-region absorption, F-region persistence, and ionospheric gradients can briefly create unusually favourable long-distance paths.

### Dawn and dusk are not identical

Sunrise and sunset can behave differently.

At **sunset**, the D region may fade quickly while the F region still has enough ionisation to support refraction. This can be very favourable for lower HF.

At **sunrise**, the D region starts rebuilding as solar radiation returns. Some paths may improve because F-region support is rising, while other lower-HF paths may worsen quickly as absorption increases.

The path also depends on which end of the circuit is at sunrise, which end is at sunset, and where the midpoint/refraction region is. The radio does not care only about the operator’s local sunrise/sunset; it cares about the illumination state along the whole ionospheric path.

### Which bands are most affected?

Gray-line effects are most commonly discussed on the lower HF bands:

- **160 m and 80 m:** D-region absorption is usually the limiting problem. Reduced absorption near dusk/dawn can make dramatic differences.
- **40 m:** Often benefits from reduced absorption while still retaining good F-region support. This is one reason 40 m can be excellent around sunrise/sunset.
- **30 m and 20 m:** Can show terminator-related changes, but the mechanism is often more mixed: MUF, F-region geometry, solar-cycle state, path length, and noise all matter.
- **10 m and 6 m:** Not usually “gray-line” in the classic low-band sense; these bands are more often dominated by F2, sporadic E, TEP, or other high-MUF mechanisms.

### Practical operating notes

- Check **both ends** of the path, not just your own sunrise/sunset.
- The best window may be short: minutes to perhaps an hour or two depending on band, distance, season, and solar conditions.
- Long paths and antipodal-ish paths can behave strangely because a large part of the path may lie near changing illumination.
- Gray-line openings can be real without being repeatable every day.
- If an opening appears only around sunrise/sunset, note absolute UTC time, local sunrise/sunset at both ends, band, path direction, and whether the path is short path or long path.

### Plain summary

Gray-line propagation is not a separate kind of radio wave. It is the normal ionosphere caught during one of its fastest daily transitions.

The useful combination is often:

```text
less D-layer absorption
+
still-useful F-region refraction
+
terminator gradients/tilts/disturbances
=
briefly improved or unusual HF paths
```

### References for this section

- Australian Government / Space Weather Services, “Digital HF Prediction Tool Help” — notes day/night sectors at ionospheric height and that HF circuit support changes rapidly near a day/night terminator: https://www.sws.bom.gov.au/Category/HF%20Systems/Online%20Tools/Prediction%20Tools/DigitalHF/help.php
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — discusses D-region absorption, day/night changes, and the role of solar illumination: https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Lo, S.; et al., “A Systematic Study of 7 MHz Greyline Propagation Using Amateur Radio Beacon Signals,” *Atmosphere*, 2022 — peer-reviewed statistical study using WSPR observations: https://www.mdpi.com/2073-4433/13/8/1340
- Cameron, T. G.; et al., “High-Latitude Off-Great Circle Propagation Associated With Large-Scale Ionospheric Gradients Along the Solar Terminator,” *Radio Science*, 2024 — terminator gradients can deflect HF waves from great-circle paths: https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2023RS007917
- Melnikov, A.; et al., “Influence of solar terminator passages on Schumann resonance parameters,” *Journal of Atmospheric and Solar-Terrestrial Physics*, 2004 — notes significant electromagnetic effects in the terminator region across a wide frequency range: https://www.sciencedirect.com/science/article/abs/pii/S1364682604001142

## 7. Critical frequency, foF2, MUF, LUF, OWF, and usable bands

[Previous](#6a-gray-line-and-terminator-propagation) | [Home / Index](#index) | [Next](#7a-space-weather-solar-cycles-and-why-the-bands-can-sound-dead)

HF operators often talk about “the band being open.” Technically, a path is usable only if the operating frequency sits between two limits:

- high enough to avoid excessive absorption and noise,
- low enough to be refracted back by the ionosphere for that path.

### Critical frequency and foF2

The critical frequency is the highest frequency returned at vertical incidence by a given ionospheric region. For the F2 region, this is called **foF2**. The Australian Space Weather Service explains that ionosondes sweep frequency and measure return delay, creating an ionogram; the highest frequency reflected vertically by F2 is foF2.

foF2 is not the same as long-distance MUF. A signal launched obliquely can often be returned at a higher frequency than the vertical critical frequency. That is the obliquity effect. This is why 20 m can work on a low-angle path even if vertical incidence would not support 14 MHz.

### MUF

The **maximum usable frequency** is the highest frequency expected to support a given path at a given time. It depends on path length, layer height, electron density, and launch angle. There is not one universal MUF for the whole world; there are path MUFs.

### LUF

The **lowest usable frequency** is the lower limit set by absorption and noise. A frequency can be “returnable” by the ionosphere but still not useful if absorption and noise make the received signal unreadable.

### OWF

The **optimum working frequency** is below the MUF and is chosen for higher reliability. Prediction systems use statistical ideas because the ionosphere changes within the hour, day to day, and with larger space-weather conditions.

### Why these terms matter practically

If the operating frequency is too low:

```text
signal may be absorbed or buried in noise
```

If it is too high:

```text
signal may pass through the ionosphere
```

If it is near the edge:

```text
one mode, one angle, one region, or one patch of ionosphere may support the path while others fail
```

This edge condition is where fading, odd openings, and large antenna-to-antenna readability differences can become very noticeable.

### References for this section

- Australian Government / Space Weather Services, “Global HF — Ionospheric Map” — https://www.sws.bom.gov.au/HF_Systems/6/5
- NOAA NCEI, “Vertical Incidence Soundings (Ionograms)” — https://www.ngdc.noaa.gov/stp/IONO/ionogram.html
- ITU-R Recommendation P.533, “Method for the prediction of the performance of HF circuits” — https://www.itu.int/rec/R-REC-P.533
- Burke and Poggio, *Numerical Electromagnetics Code (NEC) — Method of Moments*, Part III User’s Guide — https://www.nec2.org/other/nec2prt3.pdf
- ITU-R Recommendation P.1240, “ITU-R methods of basic MUF, operational MUF and ray-path prediction” — https://www.itu.int/rec/R-REC-P.1240
- NOAA SWPC, “STORM Time Empirical Ionospheric Correction” — https://www.swpc.noaa.gov/products/storm-time-empirical-ionospheric-correction

---


## 7A. Space weather, solar cycles, and why the bands can sound dead

[Previous](#7-critical-frequency-fof2-muf-luf-owf-and-usable-bands) | [Home / Index](#index) | [Next](#7b-the-hiss-we-hear-atmospheric-galactic-man-made-and-solar-noise)

HF propagation is solar-powered, but not in a simple “more Sun is always better” way.

The Sun creates and maintains the ionosphere through EUV and X-ray radiation. More ionisation can raise the critical frequencies and MUF, opening higher HF bands such as 15 m, 12 m, and 10 m. But strong solar activity can also produce flares, radio blackouts, solar proton events, geomagnetic storms, auroral absorption, disturbed F-region structure, and direct solar radio noise.

So two operators can both say “space weather is bad” and mean different things:

```text
Too little ionisation: 10 m and 15 m are dead because the MUF is too low.
Too much D-region absorption: lower HF is swallowed on the sunlit side.
Geomagnetic disturbance: F-region paths are unstable, depleted, fluttery, or gone.
Solar radio burst: the Sun itself raises the received noise or causes interference.
High local/man-made noise: the path may exist, but the receiver cannot hear it.
```

### The solar cycle: why solar maximum helps and hurts

The solar cycle is roughly an 11-year cycle in the Sun’s magnetic activity. Around solar maximum, sunspots and active regions are more common. NASA and NOAA announced in October 2024 that the Sun had reached the maximum phase of Solar Cycle 25, and noted that solar maximum brings more eruptions, radiation, and space-weather effects on systems including radio and GPS.

For HF, this has two opposing effects:

**Helpful effect:** more solar EUV generally means more F-region ionisation, higher foF2, higher MUF, and more openings on upper HF.

**Harmful effect:** more active regions means more flares, CMEs, radiation storms, geomagnetic storms, disturbed ionosphere, and sometimes solar radio noise.

This is why solar maximum can be wonderful for 10 m DX and awful for a given day’s reliability.

At solar minimum, the reverse is often true:

- fewer flares and less storminess,
- quieter geomagnetic conditions more often,
- but lower F-region ionisation,
- lower MUF,
- fewer upper-HF openings.

So the phrase “good propagation” needs a band and path attached to it. Solar minimum may be good for quiet low-band work. Solar maximum may be good for 10 m and 12 m openings. A flare can ruin the sunlit HF bands while the same high solar cycle produces excellent 10 m openings on other days.

### What “the bands are dead” can actually mean

When someone says “the bands are dead,” there are several possible causes.

#### 1. The MUF is below the band

The ionosphere may not be dense enough to refract that frequency over that path. This often affects 20 m, 17 m, 15 m, 12 m, and 10 m during low solar activity, wrong time of day, or wrong path geometry.

The band may be quiet because signals are escaping into space.

#### 2. The LUF is above the band

Absorption may be so high that lower HF is being eaten before it can make a useful path. This is common for 80 m and 40 m during daytime, and can become severe during solar flare or proton absorption events.

The band may be noisy or dull because the signal is being absorbed.

#### 3. The path is disturbed by geomagnetic activity

Geomagnetic storms can disturb the F region, especially at high latitudes. Paths can become fluttery, skewed, depleted, or unstable. The band may not be truly closed everywhere, but the particular path may be poor.

#### 4. The receiver noise floor is too high

The path may exist, but atmospheric noise, man-made noise, galactic noise, or solar radio noise may bury it. In this case, the S-meter may sit high even though useful signals are unreadable.

#### 5. The antenna is sampling the wrong part of the arrival field

A signal may arrive at angles or polarizations that one antenna receives poorly. Another antenna at the same site may hear it. This is why A/B antenna tests can show differences larger than simple gain numbers suggest.

### Solar flares and shortwave fadeouts

A solar flare produces X-ray and EUV radiation that reaches Earth at the speed of light. On the sunlit side of Earth, this can rapidly increase ionisation in the lower, denser D region. The result is increased electron-neutral collision loss and sometimes severe absorption of HF signals.

NOAA describes radio blackouts as mainly affecting the 3–30 MHz band, with signals degraded or completely absorbed when D-layer ionisation is enhanced by strong flares. The effect is strongest on the sunlit side and most intense where the Sun is high overhead.

This is the classic **shortwave fadeout** or **radio blackout** case.

Important features:

- onset can be very fast, because flare photons travel at light speed,
- mainly affects the sunlit hemisphere,
- lower HF is often hit harder, but strong events can affect much of HF,
- recovery can take minutes to hours depending on flare strength and ionospheric chemistry,
- it is absorption, not simply “no reflection.”

NOAA’s D-RAP product exists specifically because D-region absorption has a dramatic operational effect on HF and LF systems.

### Solar radiation storms and polar cap absorption

Solar energetic protons can be guided by Earth’s magnetic field into the polar atmosphere. There they enhance D-region ionisation and cause absorption, especially on polar and high-latitude paths.

This matters even if the operator is not near the pole. A long path from VK to Europe or North America may pass through high-latitude or polar-ish regions depending on route. During polar cap absorption events, some high-latitude HF paths can become poor or unusable while lower-latitude paths still work.

### Geomagnetic storms

CMEs and high-speed solar wind streams can disturb Earth’s magnetic environment. The ionosphere then changes because the magnetosphere, thermosphere, neutral winds, electric fields, and plasma are coupled.

For HF, geomagnetic storms can cause:

- lower MUF on some paths,
- storm-enhanced density in some regions and depletion in others,
- increased absorption at high latitudes,
- auroral effects and flutter,
- spread-F and irregularities,
- skewed paths,
- rapid QSB and Doppler spread,
- poor reliability even when a prediction chart looked favourable.

This is why the Kp index and geomagnetic storm levels are useful clues, but not perfect predictors. The effect is path-specific.

### Solar radio bursts: when the Sun itself becomes noise

There is another distinct problem: **direct solar radio noise**.

A flare can be accompanied by solar radio bursts. These are not the same as D-layer absorption. They are radio emissions from the Sun itself. If the Sun is in or near the antenna’s receiving pattern, a strong burst can raise the noise floor or interfere directly.

NOAA/NCEI describes large solar radio bursts as lasting about 10–20 minutes on average, while longer radio noise storms can persist with high, variable levels for hours to days. NOAA’s glossary defines a continuum storm as solar radio noise lasting hours and sometimes days across a wide range of meter and decimeter wavelengths.

For amateur HF, this means:

- a flare can cause **absorption** through D-region enhancement,
- and a solar radio burst can cause **noise/interference** by adding solar radio emission,
- these can occur together but they are not the same mechanism.

A band can therefore be unusable because the signal is absorbed, because the noise is high, or both.

### What to check when conditions are bad

Do not diagnose “dead band” from one symptom. Check the likely causes:

- **foF2/MUF maps or ionosonde data:** is the band above the usable frequency for that path?
- **D-RAP or X-ray flare status:** is there D-region absorption on the sunlit side?
- **Kp/geomagnetic storm status:** are F-region paths disturbed, especially high-latitude routes?
- **solar proton/radiation storm status:** is polar absorption likely?
- **solar radio burst/noise storm reports:** is the Sun itself raising the noise?
- **local S-meter/noise floor:** is your receiver hearing propagation failure or just local noise?
- **other bands:** if 20 m is dead, is 40 m working? If 40 m is absorbed, is 20 m open? This helps separate MUF and LUF problems.

### Plain summary

Space weather controls HF in two opposite ways:

```text
Enough solar radiation creates the useful ionosphere.
Too much or too disturbed solar activity can wreck the path.
```

So “the bands are dead” is not one diagnosis. It can mean the band is too high, too low, too absorbed, too disturbed, too noisy, or wrong for the path at that moment.

### References for this section

- NOAA Space Weather Prediction Center, “HF Radio Communications” — explains several ways space weather modifies, blocks, or disrupts HF radio paths: https://www.swpc.noaa.gov/impacts/hf-radio-communications
- NOAA Space Weather Prediction Center, “Solar Flares (Radio Blackouts)” — explains flare X-ray/EUV ionisation of the D layer and HF degradation/absorption: https://www.swpc.noaa.gov/phenomena/solar-flares-radio-blackouts
- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — operational D-region absorption product using GOES X-ray and proton data: https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- NOAA Space Weather Prediction Center, “NOAA Space Weather Scales” — R, S, and G scales for radio blackouts, solar radiation storms, and geomagnetic storms: https://www.swpc.noaa.gov/noaa-scales-explanation
- NASA/NOAA, “Sun Reaches Maximum Phase in 11-Year Solar Cycle,” 2024 — describes solar maximum, sunspots, eruptions, and impacts on radio/GPS/power systems: https://science.nasa.gov/science-research/heliophysics/nasa-noaa-sun-reaches-maximum-phase-in-11-year-solar-cycle/
- NOAA Space Weather Prediction Center, “Solar Cycle Progression” — sunspot number and F10.7 cm radio flux tracking: https://www.swpc.noaa.gov/products/solar-cycle-progression
- Australian Government / Space Weather Services, “Space Weather and Radio Communications” — notes that solar events can disrupt HF but severe all-HF disruptions are relatively rare across an 11-year cycle: https://www.sws.bom.gov.au/Educational/1/2/5
- NOAA NCEI, “Solar Radio Datasets” — describes solar radio bursts, typical duration of large bursts, and longer noise storms from sunspot groups: https://www.ncei.noaa.gov/products/space-weather/legacy-data/solar-radio-datasets
- NOAA Space Weather Prediction Center, “Space Weather Glossary” — definition of continuum storm as solar radio noise lasting hours to days over meter/decimeter wavelengths: https://www.swpc.noaa.gov/content/space-weather-glossary
- Fiori, R. A. D.; et al., “Occurrence rate and duration of space weather impacts on high-frequency radio communication used by aviation,” *Space Weather and Space Climate*, 2022: https://www.swsc-journal.org/articles/swsc/full_html/2022/01/swsc220003/swsc220003.html
- Knipp, D. J.; et al., “The May 1967 great storm and radio disruption event,” *Space Weather*, 2016 — historical example of solar radio burst/radio disruption importance: https://agupubs.onlinelibrary.wiley.com/doi/full/10.1002/2016SW001423

---

## 7B. The hiss we hear: atmospheric, galactic, man-made, and solar noise

[Previous](#7a-space-weather-solar-cycles-and-why-the-bands-can-sound-dead) | [Home / Index](#index) | [Next](#8-launch-angle-antenna-lobes-and-why-the-antenna-does-not-launch-one-ray)

The “hiss” in an HF receiver is not one thing.

With the antenna disconnected, much of the hiss may be internal receiver noise. With a real outdoor antenna connected, especially below about 30 MHz, the noise is often dominated by **external noise** rather than receiver noise.

Main contributors are:

1. **Atmospheric noise**  
   Mostly lightning and related impulsive activity around the world. It is especially important on lower HF and in tropical/summer storm seasons. It can arrive by ionospheric paths from very distant storms.

2. **Man-made noise**  
   Switch-mode power supplies, solar inverters, LED lights, VDSL, power lines, motors, fences, chargers, and countless other devices. In suburbs this can dominate everything.

3. **Galactic noise**  
   Diffuse radio emission from the Milky Way and other cosmic sources. At quiet sites, and especially at higher HF and at night, it can become a visible part of the noise background.

4. **Solar radio noise**  
   Usually not the everyday HF hiss, but during solar radio bursts or noise storms the Sun can become a strong direct noise/interference source.

5. **Receiver noise**  
   Important with small inefficient antennas or high frequencies, but often not the limiting noise source on ordinary HF wire antennas.

### Why night-time hiss can change

At night, D-region absorption is much lower. That lets wanted HF skywave signals travel better. But it can also let more distant noise reach the receiver.

An Australian Defence/University of Adelaide HF noise-modelling paper notes that under nighttime conditions at Laverton, the model showed less lightning noise and more galactic noise; with reduced D-region absorption, the directional distribution of galactic noise became more visible.

That is an important practical point: a band can improve for propagation while the noise background also changes.

### Galactic noise and polarization

Galactic radio emission, especially synchrotron emission, can be intrinsically polarized. However, at HF the practical situation at an amateur receiver is messy:

- the antenna receives a broad part of the sky, not one clean point source;
- the ionosphere can rotate polarization by Faraday rotation;
- O/X modes, multipath, and scattering can alter the received polarization;
- different sky directions contribute different polarization angles;
- the simple receiver output is total noise power in the antenna’s accepted polarization, not a clean polarization measurement.

So it is unsafe to say:

> The hiss is vertically polarized.

or:

> The hiss is horizontally polarized.

Better:

> The received noise has whatever polarization mixture survives the sky, ionosphere, and antenna pattern. A different antenna can receive a different noise field, just as it can receive a different signal field.

This matters for antenna comparisons. An antenna that receives more wanted signal but also more noise may not improve readability. An antenna that receives a cleaner signal mixture or rejects some noise directions/polarizations can improve copy even without large raw gain.

### The hiss and NKO-style observations

For NKO-style antenna tests, the important metric is not only signal strength. It is **signal-to-noise and signal-to-distortion**.

An antenna may sound better because it:

- receives more wanted signal,
- receives less noise from a troublesome direction,
- samples a better polarization mixture,
- reduces selective fading of the speech passband,
- or presents a more stable received audio envelope.

This is why a readability report can be more meaningful than an S-meter report, provided the test is done carefully.

### Plain summary

The HF hiss is usually a mixture of the atmosphere, human electrical noise, the Galaxy, the Sun, and the receiver itself.

Galactic noise can be polarized in a physical radio-astronomy sense, but the hiss heard on an ordinary HF receiver is not a simple single-polarization object. The ionosphere and antenna decide what part of the noise field you hear.

### References for this section

- ITU-R Recommendation P.372, “Radio noise” — international reference for background RF noise from lightning, man-made sources, the Galaxy, and atmospheric/ground contributions: https://www.itu.int/rec/R-REC-P.372
- ITU-R Recommendation P.372-17, “Radio noise,” 2024 PDF — updated recommendation covering radio noise from 0.1 Hz to 100 GHz: https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.372-17-202408-I!!PDF-E.pdf
- Pederick, L. H.; Cervera, M. A., “A directional HF noise model: Calibration and validation in the Australian region,” *Radio Science*, 2016 — Australian HF noise modelling, including nighttime galactic-noise visibility and D-region absorption effects: https://www.dst.defence.gov.au/sites/default/files/basic_pages/documents/2016%20Pederick%20and%20Cervera%20-%20SPINE%20Noise.pdf
- NOAA NCEI, “Solar Radio Datasets” — solar radio bursts and noise storms: https://www.ncei.noaa.gov/products/space-weather/legacy-data/solar-radio-datasets
- NOAA Space Weather Prediction Center, “Space Weather Glossary” — continuum storm definition: https://www.swpc.noaa.gov/content/space-weather-glossary
- Landecker, T. L.; et al., “A survey of the polarized emission from the Galactic plane at 1420 MHz with arcminute angular resolution,” *Astronomy & Astrophysics*, 2010 — example of polarized Galactic radio emission at higher radio frequencies: https://www.aanda.org/articles/aa/pdf/2010/12/aa13921-09.pdf

## 8. Launch angle, antenna lobes, and why the antenna does not launch one ray

[Previous](#7b-the-hiss-we-hear-atmospheric-galactic-man-made-and-solar-noise) | [Home / Index](#index) | [Next](#8a-ducted-and-chordal-modes)

Antenna plots can mislead if interpreted too literally. A NEC elevation pattern is not one beam, one ray, or one clean path. It is a distribution of radiated field strength versus angle.

If a 20 m antenna plot looks like a sideways jelly bean, that means energy is being launched over a range of angles, with more energy in some directions and less in others. Each angle can sample a different part of the ionosphere, return at a different distance, and arrive at a different time and phase.

So the antenna launches a **family of possible rays**, not one ray.

The Australian Space Weather Service notes that HF skywave paths depend on the transmitting antenna gain pattern, operating frequency, and state of the ionosphere. That is the key link between antenna design and propagation: the antenna determines how much energy is offered into each possible mode.

### High angle

High-angle energy is useful for short and medium paths, including NVIS-style work. On 40 m in the day, high-angle energy can be excellent for local and interstate. On 20 m, if the ionosphere cannot return that high angle, it may be wasted or pass through.

### Low angle

Low-angle energy is usually more useful for longer DX paths. But it is not automatically better for all HF communication. Low angle can skip over nearby stations, and on some paths it may enter a different fading/multipath mixture.

### Multiple lobes

On higher bands, wire antennas can develop multiple lobes and nulls. That means the antenna can favour some azimuth/elevation combinations and suppress others. Under real ionospheric conditions, a small pattern difference can become a large readability difference if it changes which path dominates.

### The field-sampling point

On receive, the antenna also samples the incoming field according to its pattern and polarization response. It does not receive “the signal” as an abstract object. It receives whatever part of the arriving electric field matches the antenna's available response.

This matters for comparing antennas. One antenna may have more modelled gain in one simple direction, while another samples a broader or more useful mixture of arrival angles and polarizations.

### References for this section

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, section on propagation modes and antenna gain pattern — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- ITU-R Recommendation P.533, which explicitly requires antenna performance information for practical HF prediction — https://www.itu.int/rec/R-REC-P.533
- National Bureau of Standards / NIST, “Ionospheric Radio Propagation” — https://nvlpubs.nist.gov/nistpubs/Legacy/circ/nbscircular462.pdf

---

## 8A. Ducted and chordal modes

[Previous](#8-launch-angle-antenna-lobes-and-why-the-antenna-does-not-launch-one-ray) | [Home / Index](#index) | [Next](#8b-nec-modelling-what-it-can-and-cannot-tell-you-about-hf-copy)

Ducted and chordal modes are easy to understate because they are not the normal textbook one-hop or two-hop skywave picture. They are still ionospheric propagation, but the ray does not simply go:

```text
Earth → ionosphere → Earth → ionosphere → Earth
```

Instead, for part of the path, the wave can stay within the ionospheric system and undergo further refraction before it comes back to ground. The Australian Space Weather Service explicitly groups **ducting and chordal modes** with more complex HF skywave modes and says they involve several ionospheric refractions without intermediate ground reflections. It also notes that they can produce strong signals because the wave spends less time crossing the absorbing daytime D region and avoids some ground-reflection attenuation.

That makes them important for long-path HF, unusual strong signals, above-normal MUF events, TEP-related paths, and some of the “why is this path suddenly so good?” reports.

### Ordinary multi-hop mode

An ordinary two-hop F-region path is roughly:

```text
Tx → F region → ground/sea → F region → Rx
```

That intermediate ground or sea contact matters. It can add loss, alter phase, change polarization, scatter energy, and force the signal to pass through the lower ionosphere again. If the path is sunlit, each D-region traversal can add absorption.

This is the simple picture used in many prediction tools and teaching diagrams. It is useful, but not complete.

### Chordal mode / chordal-hop propagation

A chordal mode is closer to:

```text
Tx → F region → F region again → maybe another F/E region interaction → Rx
```

The key feature is:

> successive ionospheric refractions without an intermediate ground reflection.

The word **chordal** comes from the path resembling a chord cutting through the curved ionospheric shell rather than bouncing from the ground after every refraction. The ray can be refracted in one ionospheric region and then encounter another tilted or curved region before reaching Earth.

ITU-R P.2011 describes chordal-hop propagation as being enabled by ionospheric tilts, especially on either side of the magnetic equator and in sub-auroral troughs. It says these tilts can allow ray paths to proceed from refraction in one location to another without an intermediate ground reflection, and notes that trans-equatorial propagation of this kind has been observed well into VHF when associated with ionospheric irregularities.

Important features:

- no ground reflection between some ionospheric refractions;
- often needs ionospheric tilt, curvature, gradients, or irregular structure;
- can be strong because it avoids ground loss and some lower-ionosphere absorption;
- can be associated with equatorial anomaly structure and TEP;
- can support paths that look better than a simple MUF/hop model would predict;
- can be narrow in geography and time because it depends on geometry.

In plain terms:

> the ionosphere can sometimes hand the ray from one refracting region to another before the ray touches the ground.

That is very different from a normal multi-hop path.

### Ducted mode

A ducted mode is more like a temporary waveguide or channel inside the ionosphere. Instead of a ray making a clear single refraction and then leaving, the wave becomes partly trapped between refractive regions or within a favourable electron-density height profile.

A simple sketch is:

```text
upper refractive boundary
   \____________________________________
    guided / trapped HF energy → → → →
   /____________________________________/
lower refractive boundary
```

This is only a cartoon, but it captures the main idea: the wave is guided for some distance by the ionospheric structure.

ITU-R P.2011 says low-angle radiation can sometimes enter ducts formed by particular electron-density height profiles, allowing propagation to long ranges and at frequencies higher than the basic MUF. ITU-R P.531 also notes that near-tangential paths within the ionosphere may be ducted and can propagate to longer ranges, while being subject to ionospheric irregularity effects.

Important features:

- commonly favours low-angle radiation;
- depends on electron-density height profiles, tilts, gradients, or disturbances;
- can carry energy farther than expected;
- can contribute to propagation above the basic MUF;
- may be sensitive to TIDs, equatorial anomaly structure, troughs, and irregularities;
- can produce strong but sometimes selective or unstable paths.

In plain terms:

> a ducted mode is when the ionosphere temporarily acts a little like a leaky waveguide.

It is not a metal pipe, and it is not perfectly lossless. But compared with repeated ground-reflected hops, it can be efficient enough to stand out.

### Chordal versus ducted: practical difference

They overlap in real use, and some sources discuss them together, but they are worth separating mentally.

| Mode | Simple picture | Main feature | Why it can be strong | Common clues |
|---|---|---|---|---|
| **Chordal mode** | Ray is refracted from one ionospheric region to another before reaching ground | Successive ionospheric refractions without intermediate ground reflection | Avoids ground loss and some D-region traversal | Long path sounds unexpectedly strong; path may relate to ionospheric tilts, TEP, equatorial anomaly, terminator gradients, or disturbed regions |
| **Ducted mode** | Wave is partly guided within an ionospheric channel | Trapping/guiding by electron-density height profile or refractive boundaries | Long guided section may avoid normal hop losses | Low-angle signals, long range, above-MUF behaviour, sudden opening/closing, sometimes narrow geography |

The boundary between the two can be fuzzy in field language. A real path may include ordinary hops, chordal sections, ducted sections, scatter, and ground/sea reflections. The receiver only hears the sum.

### Why they matter for MUF

The **basic MUF** is the highest frequency expected to propagate between two terminals by normal ionospheric refraction for the assumed mode and geometry. But ITU-R P.2011 is specifically about propagation above the basic MUF, and lists ducted modes, chordal-hop propagation, ionospheric roughness, scatter, sporadic E, auroral scatter, and other mechanisms as contributors.

So when a band appears open above what a simple prediction suggested, it may not mean the prediction was “stupid.” It may mean the real ionosphere supplied a non-basic mode:

```text
ordinary predicted path: not supported
real complex path: supported by tilt, ducting, chordal hop, scatter, Es, or TEP
```

This is especially relevant near:

- the magnetic equator and equatorial anomaly;
- sub-auroral troughs;
- day-night terminators;
- TID-disturbed regions;
- strong horizontal gradients;
- periods of spread-F or irregularity;
- long, low-angle paths.

### Relationship to TIDs and tilts

TIDs are relevant because they ripple and tilt the electron-density surfaces. A small tilt in a refracting region can steer a low-angle ray into a geometry that a smooth-layer model would not predict.

The Australian Space Weather Service specifically notes that an undulating ionosphere changes the height and angle of refraction, and that tilting near equatorial anomalies, mid-latitude troughs, terminators, and disturbed ionosphere can cause unusual propagation such as ducting and chordal modes. It also notes that TIDs may initiate chordal and ducted modes.

That makes TIDs more than a fading mechanism. They can sometimes be a path-creation mechanism.

### Relationship to TEP

TEP and chordal propagation are closely related in some cases. The equatorial ionisation anomaly produces strong electron-density gradients and tilted structures on either side of the magnetic equator. These can support long trans-equatorial chordal modes, especially on higher HF and sometimes VHF.

This helps explain why a VK-to-Asia or VK-to-Indonesia path can sometimes sound unusually strong or appear at frequencies that look optimistic under a simple F-layer hop model. The path may be using the equatorial anomaly geometry rather than acting like an ordinary two-hop F2 route.

### Relationship to gray-line and terminator propagation

The terminator is another place where strong gradients and rapid changes occur. D-region absorption can collapse quickly on the dark side while F-region ionisation remains useful. At the same time, the terminator can introduce steep horizontal gradients and tilts.

That does not mean every gray-line opening is chordal or ducted. But terminator geometry can help create unusual steering, skewed paths, or non-basic modes. This is why gray-line propagation should not be treated as only “less D-layer absorption.” Less absorption is a big part of it, but geometry can matter too.

### How ducted/chordal modes may sound on air

Possible clues include:

- unexpectedly strong long-distance signals;
- a path that appears above the predicted basic MUF;
- short-lived openings that switch on/off sharply;
- narrow geographic footprints;
- skewed paths or stations arriving from odd bearings;
- strong signal with unusual fading or phase effects;
- different results between antennas with different low-angle and polarization response.

These clues are not proof. They are only hints. Confirmation needs ionosonde data, ray tracing, Doppler/angle measurements, wide-area reception reports, or careful comparison against prediction models.

### Practical antenna relevance

Ducted and chordal modes often favour particular launch angles, commonly low angles, and may be sensitive to polarization and O/X-mode behaviour. That means an antenna can make a large practical difference even if a simple free-space or smooth-earth model suggests only a small gain difference.

For NKO-style receive/readability reports, these modes are another reason to avoid saying:

> the antenna is simply louder.

A safer statement is:

> the antenna may be coupling into, or receiving from, a more useful mix of real propagation modes.

That includes ordinary F-layer paths, E/F mixed modes, O/X-mode mixtures, selective fading, TIDs, TEP, and sometimes ducted or chordal propagation.

### References for this section

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation,” section 2.4, which describes ducting and chordal modes, ionospheric tilting, reduced D-region/ground-reflection loss, equatorial-anomaly chordal modes, and TID initiation of chordal/ducted modes: https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- ITU-R Report P.2011, “Propagation at frequencies above the basic MUF,” sections 2.4 and 2.5, which describe ducted modes and chordal-hop propagation as mechanisms contributing to above-basic-MUF propagation: https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-P.2011-1997-PDF-E.pdf
- ITU-R Recommendation P.531-15, “Ionospheric propagation data and prediction methods required for the design of satellite networks and systems,” noting that near-tangential ionospheric propagation may occur within ducts and reach longer ranges: https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.531-15-202308-S!!PDF-E.pdf
- Platt, I. G., “MF and HF propagation characteristics of ionospheric ducts,” *Journal of Atmospheric and Terrestrial Physics*, 1989 — academic treatment of MF/HF propagation along ionospheric ducts: https://www.sciencedirect.com/science/article/pii/0021916989900330
- Carrara, N., “Guided Propagation of HF Radio Waves in the Ionosphere,” *Space Science Reviews*, 1970 — review of guided/ducted HF propagation: https://adsabs.harvard.edu/full/1970SSRv...11..555C

---

## 8B. NEC modelling: what it can and cannot tell you about HF copy

[Previous](#8a-ducted-and-chordal-modes) | [Home / Index](#index) | [Next](#9-multipath-and-qsb)

NEC-style modelling is one of the most useful tools an antenna builder has. It can show feed impedance, current distribution, approximate far-field pattern, lobe structure, nulls, and the effect of changing length, height, loading, and geometry. For an antenna such as NKO, modelling is valuable because it can test whether the long arm, short arm, vertical coax section, matching unit, and choke placement make electrical sense.

But NEC is not an oracle for real HF readability. It models the antenna system and its specified environment. It does not model the whole skywave circuit from speaker to speaker.

### What NEC is good at

NEC can be very good for:

- finding likely resonance and feed impedance,
- showing where current flows on modelled conductors,
- comparing pattern changes when geometry changes,
- seeing whether a vertical or horizontal component is likely to exist,
- checking whether a choke or feedline current path matters,
- comparing idealised elevation-angle response,
- looking for obvious design mistakes before building hardware.

For NKO-style thinking, this is useful. If the vertical coax section is meant to be a defined part of the radiating system, it should be represented in the model. If the choke is meant to stop the radiating section, the model should show what happens with and without that current path.

### What NEC does not tell you directly

A NEC pattern does not directly tell you:

- whether the D region is absorbing the path today,
- whether the F2 MUF supports the path,
- whether a TID is focusing or defocusing the signal,
- whether the signal is arriving by O-mode, X-mode, chordal mode, ducted mode, or several paths at once,
- how much Faraday rotation has changed the received polarization,
- whether the SSB passband is selectively faded,
- whether the local noise floor masks the advantage,
- whether the listener finds the audio easier to understand,
- or whether two operators will report reciprocal QSB.

That is why a modelled 20 m lobe that looks like a neat sideways jelly bean is only the beginning. The antenna may launch energy in that pattern, but the ionosphere decides which parts survive, bend, split, rotate, fade, and arrive.

### Installation details matter

NEC models only what is put into the model. If the real station has a metal roof, gutters, fences, a mast, coax shield current, a lossy or sloping ground system, nearby trees, a shed, power wiring, or a different choke position, then the real antenna may not be the clean antenna in the file.

Ground is especially important. NEC provides ideal and real-ground options, but the user still chooses the ground model. Real soil is not always flat, homogeneous, or known. A low horizontal wire, an end-fed, an OCF, or a vertical section can be strongly affected by ground assumptions.

Feedline current is also important. In many simple models the feedline is absent, yet in real antennas the coax shield can be a radiator, a loss path, a noise pickup path, or a controlled part of the design. For NKO, that distinction is central: uncontrolled common-mode current and a deliberately defined vertical coax section are not the same thing.

### Practical rule

Use NEC to answer:

> “What should this antenna do in this simplified electrical environment?”

Do not use NEC alone to answer:

> “How readable will a weak SSB signal be through today’s ionosphere?”

For that, the better workflow is:

1. model the antenna, including the conductors and current paths that actually exist;
2. measure the built antenna with a VNA, current probe, and choke tests;
3. compare antennas rapidly using A/B/A/B switching;
4. record audio, not just S-meter readings;
5. log propagation context: band, time, path, foF2/MUF if available, solar indices, D-region absorption, Kp, and obvious QSB/selective fading.

### NKO tie-in

The cautious NKO interpretation is that modelling can show whether the antenna has a plausible useful mix of horizontal and vertical current components. Field reports can then test whether that mix improves real copy.

So the careful claim is not:

> “The model proves NKO is better.”

The careful claim is:

> “The model can suggest why NKO might sample or launch a different field mixture, while field reports and controlled tests are needed to show whether that difference improves readability.”

### References for this section

- Burke and Poggio, *Numerical Electromagnetics Code (NEC) — Method of Moments*, Part III User’s Guide — source/load setup, segmentation, geometry, and ground modelling options: https://www.nec2.org/other/nec2prt3.pdf
- Lawrence Livermore / OSTI, Burke, “Ground Model Options in the NEC-4.2 Antenna Code” — discusses ground modelling in NEC-4.2, including homogeneous ground options: https://www.osti.gov/servlets/purl/1117909
- ITU-R Recommendation P.533, “Method for the prediction of the performance of HF circuits” — HF circuit performance includes propagation mode, reliability, signal-to-noise, and time/frequency spread, which are outside a simple antenna-only model: https://www.itu.int/rec/R-REC-P.533
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — discusses antenna gain pattern as only one part of the HF circuit, alongside ionospheric mode, path, D absorption, ducting, and chordal propagation: https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf

---

## 9. Multipath and QSB

[Previous](#8b-nec-modelling-what-it-can-and-cannot-tell-you-about-hf-copy) | [Home / Index](#index) | [Next](#10-selective-fading-passband-damage-and-why-ssb-can-become-impossible-to-tune)

**QSB** is fading. At HF, a major cause is multipath interference: the receiver hears several versions of the same signal arriving together.

Those versions may differ by:

- path length,
- arrival angle,
- phase,
- polarization,
- O/X mode history,
- number of hops,
- E or F region involvement,
- ground/sea reflection strength,
- Doppler shift,
- and time delay.

At the receiving antenna, the RF voltages add as vectors. If two components arrive in phase, they reinforce. If they arrive out of phase, they cancel. The ionosphere is moving and changing, so the phase relationship changes. The result is signal strength rising and falling.

### Why small path changes matter

At 7 MHz, one wavelength is about 40 m. A path change of 20 m is half a wavelength. HF paths can be thousands of kilometres long, so a tiny fractional change in effective path length can produce a large RF phase change at the receiver.

That is why a signal can fade deeply even when the transmitter power, antenna, and distance have not changed.

### Slow QSB

Slow QSB over seconds to minutes is often produced by changing multipath geometry: moving ionospheric gradients, changing effective reflection height, or slow changes in which mode dominates.

### Fast flutter

Fast flutter can occur when the ionosphere is disturbed, moving rapidly, or producing Doppler spread. Auroral, polar, TEP/eTEP, and disturbed F-region paths can sound fluttery or rough.

### The receiver hears the sum

The receiver does not know which part came from which path. It simply sees the combined RF. That combined RF may be strong, weak, phasey, or distorted depending on the current vector sum.

### References for this section

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, discussion of mixed modes, ducting, chordal modes, and fading-producing complexity — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- ITU-R Recommendation P.533, scope includes prediction of HF signal levels, reliability, time spread, and frequency spread — https://www.itu.int/rec/R-REC-P.533
- Australian Government / Space Weather Services, ASAPS documentation, which discusses fading from multiple modes of similar amplitude and phase differences — https://www.sws.bom.gov.au/Category/Products%20and%20Services/Software/ASAPS/ASAPSVer5.3.pdf
- NOAA NCEI, “Sudden Ionospheric Disturbances Data”, for HF frequency deviations during sudden ionospheric disturbances — https://www.ngdc.noaa.gov/stp/solar/sid.html

---

## 10. Selective fading, passband damage, and why SSB can become impossible to tune

[Previous](#9-multipath-and-qsb) | [Home / Index](#index) | [Next](#11-the-earths-magnetic-field-and-why-the-ionosphere-is-direction-sensitive)

A fading signal is not always just a signal getting louder and softer. Sometimes different parts of the signal bandwidth fade differently. This is **selective fading**.

For SSB, the voice occupies a few kHz of RF bandwidth. If multipath creates cancellation at one part of that bandwidth but not another, the voice spectrum is damaged. The S-meter may still show a decent signal, but speech becomes hollow, watery, thin, muffled, or impossible to tune properly.

### Why tuning does not always fix it

With ordinary mistuning, you can tune through the voice and find the natural pitch. With selective fading, there may be no correct tuning point because the passband itself has been distorted before it reaches the radio.

Typical symptoms:

- vowels improve but consonants vanish,
- consonants sharpen but voice pitch sounds wrong,
- passband shift helps slightly but does not fix it,
- speech sounds hollow or phasey,
- strong signals are still hard to understand,
- the “best tune” point keeps moving.

This matches the observation from the conversation: moving the radio passband or IF could help a small amount, but did not fully cure the unreadability. That points to ionospheric/passband distortion rather than simple operator tuning error.

### Why speech intelligibility can improve more than S-meter strength

Speech intelligibility depends heavily on preserving enough cues: consonant energy, transitions, syllable envelope, and timing. A small improvement in the received path mixture can make speech much easier to decode even if the S-meter only improves modestly.

For a listener with an auditory processing difficulty, this may matter even more. The medically safe statement is not that an antenna treats the condition, but that cleaner and more stable SSB audio may reduce the listening burden. The NIDCD describes auditory processing disorder broadly as difficulty making sense of sounds around a person; that is enough to justify caution when discussing listening effort, but it does not justify any medical claim about an antenna.

### Practical wording

Strong wording to avoid:

> The antenna fixes delayed audio response.

Better wording:

> A user with an auditory processing difficulty reported that the NKO audio was easier to follow. This is a subjective readability report, not a medical claim.

### References for this section

- ITU-R Recommendation P.533, because the official HF prediction framework considers not only signal-to-noise but also expected time and frequency spreads of the channel — https://www.itu.int/rec/R-REC-P.533
- Australian Government / Space Weather Services, ASAPS documentation, discussion of fading from multiple modes and phase differences — https://www.sws.bom.gov.au/Category/Products%20and%20Services/Software/ASAPS/ASAPSVer5.3.pdf
- NOAA NCEI, “Sudden Ionospheric Disturbances Data”, including sudden frequency deviation of HF waves reflected from the ionosphere — https://www.ngdc.noaa.gov/stp/solar/sid.html
- U.S. National Institute on Deafness and Other Communication Disorders, “Auditory Processing Disorder” — https://www.nidcd.nih.gov/health/auditory-processing-disorder

---

## 11. The Earth's magnetic field and why the ionosphere is direction-sensitive

[Previous](#10-selective-fading-passband-damage-and-why-ssb-can-become-impossible-to-tune) | [Home / Index](#index) | [Next](#12-ordinary-and-extraordinary-waves-o-mode-and-x-mode)

The Earth's magnetic field is not just a flat north-south line. At any point it has a 3-D direction and strength:

- horizontal component,
- vertical component,
- local inclination/dip,
- local declination,
- and field strength.

In southern Australia, the field is not simply “northward.” It is tilted in 3-D. The exact local direction varies with location and time.

In ordinary air, the magnetic field has little practical effect on an HF wave. In the ionosphere, it matters because the medium contains free electrons. The RF electric field moves electrons; the geomagnetic field pushes moving charges sideways. Electron motion becomes rotational/elliptical rather than simple straight-line sloshing.

This makes the ionosphere **anisotropic**, meaning its response depends on direction and polarization. A wave travelling along the magnetic field is treated differently from a wave travelling across it. This affects:

- O/X mode behaviour,
- polarization rotation,
- absorption differences,
- ray path details,
- high-latitude and equatorial propagation,
- TEP and field-aligned irregularities,
- and practical reciprocity of polarization coupling.

### North-south versus east-west paths

A north-south geographic path and an east-west geographic path do not necessarily make the same angle to the geomagnetic field. The important angle is not just the map bearing; it is the angle between the wave vector and the local magnetic field along the ionospheric path.

This is one reason propagation can differ by path direction even if distances and frequencies seem similar.

### References for this section

- Naval Postgraduate School, “Ionospheric Radiowave Propagation”, discussion of Earth magnetic field causing the ionosphere to behave as an anisotropic medium — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- Australian Government / Space Weather Services, “Transequatorial Radio Propagation”, discussion of the magnetic equator, geomagnetic equator, equatorial anomaly, and magnetic-field-driven plasma motion — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
- NASA, “10 Things to Know About the Ionosphere” — https://science.nasa.gov/earth/10-things-to-know-about-the-ionosphere/
- NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere

---

## 12. Ordinary and extraordinary waves: O-mode and X-mode

[Previous](#11-the-earths-magnetic-field-and-why-the-ionosphere-is-direction-sensitive) | [Home / Index](#index) | [Next](#13-faraday-rotation-and-practical-reciprocity)

When an HF wave enters the magnetised ionosphere, the plasma does not support every arbitrary polarisation in the same way. The incoming field can be decomposed into two natural magneto-ionic modes:

- **ordinary wave**, or **O-mode**,
- **extraordinary wave**, or **X-mode**.

This is often described as the wave “splitting,” but that word can be misleading.

The better explanation is:

> The incoming electromagnetic field is resolved into the two natural propagation modes of the magnetised plasma.

They are not two separate messages that have to find each other again. They are components of the same field, each with different propagation constants in the ionosphere.

The Australian Space Weather Service says that the geomagnetic field splits a radio wave in the ionosphere into ordinary and extraordinary components, and that the ordinary wave is routinely scaled from ionograms. The Naval Postgraduate School teaching notes state that an arbitrarily polarised wave can be decomposed into ordinary and extraordinary polarisations upon entering the ionosphere and recombined on exiting, with a changed polarisation angle: Faraday rotation.

### What differs between O and X?

The O and X modes can differ in:

- refractive index,
- phase velocity,
- group delay,
- absorption,
- critical frequency behaviour,
- polarization state,
- path bending,
- and time of arrival.

The X-mode is more directly shaped by the magnetic field. The O-mode is closer to the unmagnetised-plasma response, though that is a simplification.

### Do they physically separate?

Sometimes the mode separation is mainly a propagation-mode description; the components still occupy nearly the same region and exit as a combined field. Sometimes the O and X components can take measurably different paths and arrive separately enough to contribute to multipath.

### What happens on later hops?

Once the wave leaves the ionosphere, the O/X labels no longer apply in the same way. It is just a free-space electromagnetic wave with some amplitude, phase, direction, and polarization. If it reflects from ground/sea and re-enters the ionosphere, the ionosphere again resolves that incoming field into whatever mixture of O and X modes fits the new direction and polarization.

So a multi-hop path can contain sequences such as O→O, O→X, X→O, and X→X in a ray/mode analysis, but real propagation usually does not form a clean doubling tree. One mode may dominate, one may be lost, modes may overlap, and the receiver hears the combined result.

### References for this section

- Naval Postgraduate School, “Ionospheric Radiowave Propagation” — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- Australian Government / Space Weather Services, “Global HF — Ionospheric Map”, note on ordinary and extraordinary waves — https://www.sws.bom.gov.au/HF_Systems/6/5
- NASA NTRS, H. Unz, “Ionospheric Effects on 400 Mc Radar Signals”, includes Appleton-Hartree treatment and O/X wave discussion — https://ntrs.nasa.gov/api/citations/19670002948/downloads/19670002948.pdf
- NIST legacy publication, “Ionospheric Radio Propagation” — https://nvlpubs.nist.gov/nistpubs/Legacy/circ/nbscircular462.pdf
- CEDAR presentation, “Radio Waves in the Ionosphere”, Appleton-Hartree and mode splitting — https://cedarscience.org/sites/default/files/meeting/Miller_CEDAR.pdf

---

## 13. Faraday rotation and practical reciprocity

[Previous](#12-ordinary-and-extraordinary-waves-o-mode-and-x-mode) | [Home / Index](#index) | [Next](#13a-practical-reciprocity-non-reciprocal-qsb-and-what-operators-really-hear)

Faraday rotation is the rotation of the plane of polarization as a wave travels through a magnetised plasma. In the ionosphere, it is caused by the O and X/circular components accumulating different phase shifts.

For HF and VHF paths, this means the polarization launched by the transmitting antenna is not necessarily the polarization received at the far end. A horizontal signal may arrive partly vertical, elliptical, or rotating. A vertical signal may arrive with a changed polarization too.

### Does Faraday rotation break reciprocity?

It can break simple **polarization reciprocity**. That does not mean it creates a perfect one-way path. It means the forward and reverse polarization transformations are not necessarily simple mirror images that cancel.

A cautious practical statement is:

> The path may be physically present both ways, but the polarization coupling into the antennas at the two ends can be different.

This matters especially when:

- antennas at the two ends have fixed polarization,
- the path is near its frequency limit,
- only one O/X mode is strong,
- TEP or equatorial irregularities are involved,
- the ionosphere is rapidly changing,
- or one end has a much higher noise floor.

### One-way contacts

A “one-way” contact may be caused by several things at once:

- actual path asymmetry,
- different antennas,
- different receiver noise floors,
- different transmit powers,
- polarization rotation and mismatch,
- O/X mode differences,
- rapid fading,
- different local ionosphere at each end,
- different take-off angles,
- and the path changing between overs.

So Faraday rotation is a real non-simple-reciprocity mechanism, but it is rarely the sole explanation for a one-way report.

### References for this section

- Naval Postgraduate School, “Ionospheric Radiowave Propagation”, Faraday rotation and O/X decomposition — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- NASA NTRS, H. Unz, “Ionospheric Effects on 400 Mc Radar Signals”, includes Faraday rotation estimates — https://ntrs.nasa.gov/api/citations/19670002948/downloads/19670002948.pdf
- CEDAR, “Radio Waves in the Ionosphere”, Appleton-Hartree, mode splitting, and Faraday rotation — https://cedarscience.org/sites/default/files/meeting/Miller_CEDAR.pdf
- National Bureau of Standards / NIST, “Ionospheric Radio Propagation” — https://nvlpubs.nist.gov/nistpubs/Legacy/circ/nbscircular462.pdf

---


## 13A. Practical reciprocity, non-reciprocal QSB, and what operators really hear

[Previous](#13-faraday-rotation-and-practical-reciprocity) | [Home / Index](#index) | [Next](#14-travelling-ionospheric-disturbances-or-tids)

Radio amateurs often say “reciprocity” as if it means:

> If I hear him fading, he must hear me fading in the same way.

That is not what the useful engineering idea of reciprocity says.

A better practical statement is:

> A passive antenna can have reciprocal transmit and receive properties, and an ideal stable reciprocal channel can have symmetric transfer behaviour, but a real HF QSO is not usually an ideal simultaneous channel measurement. The two operators can experience very different fading, noise, polarisation coupling, and readability.

This distinction matters because otherwise “reciprocity” becomes a slogan that hides what the ionosphere is actually doing.

### Four different things people mix together

In ordinary radio conversation, several different ideas get bundled under one word.

#### 1. Antenna reciprocity

For a passive, linear antenna system, the transmit and receive patterns are closely related. This is the normal antenna-theory meaning. It is why an antenna that radiates well in a direction also tends to receive well from that direction, assuming the same frequency, terminals, matching, polarisation, and environment.

This is a real and useful principle.

But it does **not** mean:

> Every station I can hear can hear me equally well.

Antenna reciprocity does not remove differences in transmitter power, receiver noise floor, local interference, polarisation mismatch, path timing, or ionospheric fading.

#### 2. Path reciprocity

A stable, passive, reciprocal propagation path can have symmetric behaviour if source and receiver are swapped under the same conditions. That is the clean theoretical picture.

But HF skywave paths are rarely clean. The ionosphere is moving, magnetised, layered, tilted, rippled, lossy, and often multipath. ITU-R P.533 explicitly treats HF reliability as depending not only on signal-to-noise ratio, but also on expected time spread and frequency spread of the HF channel. That alone is a warning that the practical HF channel is not just a fixed wire between two stations.

#### 3. Polarisation reciprocity

The ionosphere can rotate and change polarisation through O/X mode behaviour and Faraday rotation. A signal arriving at a receiving antenna may be linear, elliptical, rotating, or simply not well matched to the antenna at that instant.

Faraday rotation is often discussed in satellite and space-communications contexts, so a bit of folklore grows around the idea that polarisation non-reciprocity is “only a satellite thing.” That is too narrow. The ionosphere is magnetised plasma for HF skywave too. The effect may be messier and less predictable on HF, but it is not absent.

#### 4. Operator-experience reciprocity

This is the one that matters in an SSB QSO.

One operator may hear:

```text
S7 but watery, phasey, and fading
```

while the other hears:

```text
S5 but steady and easy copy
```

Both reports can be true. They are not measuring the same thing at the same instant with the same antenna, receiver, noise floor, polarisation coupling, and path mixture.

### The key practical answer: yes, one-way QSB is common

It is entirely possible for you to hear deep QSB on a distant station while the other operator does not hear comparable QSB on you.

That does not automatically prove a truly one-way ionospheric path. It simply means the received field at each station is being sampled differently.

The most common reasons are below.

### 1. The two directions are not sampled at exactly the same time

In a normal SSB QSO, the contact is half-duplex:

```text
Time 1: he transmits, you listen
Time 2: you transmit, he listens
```

A TID, moving ionospheric tilt, fading null, or polarisation rotation can change during the seconds between overs. Slow QSB can move over tens of seconds or minutes; faster flutter and polarisation fading can move more quickly.

So “the same path” is not always the same channel by the time the other station transmits.

### 2. The two antennas may couple into different angle and polarisation mixtures

Even on the same nominal frequency, the two antennas may not launch or receive the same mixture of:

- elevation angles,
- azimuth lobes,
- vertical and horizontal field components,
- O/X mode coupling,
- near-ground loss and reflection,
- local common-mode current,
- and polarisation sensitivity.

The distant station’s antenna may launch a path mixture that arrives at you as two or three similar-strength components. Those components can interfere and fade deeply.

Your antenna may launch a cleaner dominant component back to him, or his receiving antenna may sample the mixture differently.

That gives:

```text
Him → you: multipath-heavy, deep QSB
You → him: one component dominates, little QSB
```

This is especially relevant when comparing antennas with different vertical/horizontal contribution, feedline radiation, height, ground interaction, or polarisation response.

### 3. Multipath fading is local at the receiving antenna terminals

QSB is the result of vector addition of arriving RF fields at the receiving antenna. A deep fade can be caused by several components arriving with phases that cancel at your antenna terminals.

A few wavelengths away, or with a different antenna polarisation or height, the same components may add differently.

So fading is not simply “on the whole path.” It is often a local result of how the path mixture sums at one receiving antenna.

This is why antenna diversity works: two receiving antennas separated by distance, height, pattern, or polarisation can experience different fades on the same signal.

### 4. TIDs can focus one end and defocus the other

A TID is a travelling ripple or tilt in ionospheric electron density. Australian Space Weather Services notes that TIDs can tilt an ionospheric region, causing signals to be focused or defocused, and can cause changes in phase, amplitude, polarisation, and angle of arrival.

That is almost a recipe for practical non-reciprocal fading.

A TID may place your receiving site near the edge of a moving focus/defocus pattern while the other station’s receiving site is in a steadier part of the pattern. On the next over, the pattern may have moved.

Useful mental picture:

```text
The ionosphere is acting like a slowly moving, uneven lens.
One end of the QSO may be sitting in the moving bright/dark pattern.
The other end may not be.
```

That does not require the path to be a one-way pipe. It only requires the focusing pattern to be different at the two receiving points and times.

### 5. Ducted and chordal modes can be selective

Ducted and chordal modes are not ordinary ground-reflection hop paths. They can involve multiple ionospheric refractions without an intermediate ground reflection. SWS notes that these modes can produce strong signals because the wave spends less time in the absorbing D region and avoids some ground-reflection loss. ITU-R Report P.2011 lists ducted modes and chordal-hop propagation among mechanisms that can support propagation above the basic MUF.

These modes are sensitive to launch angle, ionospheric tilt, electron-density profile, and coupling into the available structure.

So one direction may couple well into a ducted/chordal path while the other direction couples into a different mixture, or into the same structure less efficiently. In a QSO, that can look like:

```text
A hears B with heavy fading or distortion
B hears A steady and strong
```

Again, that is not necessarily a violation of all physics. It is a practical result of different coupling, different timing, and a changing medium.

### 6. O/X modes and Faraday rotation can change the receiving match

An incoming HF wave in the ionosphere can be resolved into ordinary and extraordinary magneto-ionic modes. These modes can have different phase velocity, absorption, delay, and polarisation behaviour. Faraday rotation can then change the arriving polarisation.

If your antenna is mainly sensitive to one polarisation component, and the arriving field is rotating or becoming elliptical, you may hear polarisation fading. The other station’s receiving antenna may be less affected, or may be favourably aligned at that moment.

This is one reason “I am fading on you, but you are not fading on me” is not surprising.

### 7. Noise floors are not reciprocal

This is the most ordinary reason of all, and it is often forgotten.

The ionospheric signal path may be broadly similar both ways, but the receive environments are not. One station may have:

- suburban electrical noise,
- solar inverter hash,
- powerline noise,
- local QRN,
- nearby splatter,
- a receiver AGC issue,
- a wider or narrower filter,
- or a poorer local ground/noise environment.

The other station may be rural and quiet.

So one operator may report “deep fading” when part of the problem is really signal-to-noise ratio changing at that receiver. The other operator may hear a steady signal because his noise floor is low enough that the same amplitude variation does not damage readability.

### 8. SSB readability is not the same as signal strength

A voice signal can be loud but difficult to copy. Selective fading can damage the speech passband unevenly. Some voice frequencies are reinforced while others are cancelled or phase-shifted.

This produces the “I cannot quite tune him” effect:

- tune one way and the consonants appear but the voice becomes thin,
- tune the other way and the vowels sound better but the speech goes muddy,
- move the IF/passband and it helps a little but does not cure the problem,
- the S-meter may not fully explain the copyability.

So one station may hear QSB as unreadable, watery speech while the other hears only mild strength variation.

### Does this only apply to satellite work?

No.

Satellite work makes non-reciprocity obvious because uplink and downlink may use different frequencies, different antennas, different Doppler shifts, different polarisation rotations, and different ionospheric pierce points. So operators learn quickly not to assume the two directions are identical.

But the underlying caution also applies to HF skywave:

- HF paths are time-varying.
- HF paths are multipath.
- HF paths are polarisation-changing.
- HF paths can include O/X mode effects.
- HF paths can be tilted, ducted, chordal, or disturbed by TIDs.
- HF receive noise is strongly local.

The same-frequency HF path may be **more nearly reciprocal** than a split-frequency satellite link, but “more nearly” is not “perfectly” in the practical QSO sense.

### Practical field interpretation

When two stations compare reports, use this wording:

> Reciprocal antenna behaviour does not guarantee reciprocal fading or reciprocal readability. In real HF operation, one station may hear QSB while the other hears a steady signal because the two received fields are sampled at different times, through different antennas, different polarisation coupling, different multipath mixtures, and different local noise floors.

For field testing, log both directions separately:

```text
Time:
Band/frequency:
Antenna at station A:
Antenna at station B:
Report A hears B: strength, QSB, readability, audio character
Report B hears A: strength, QSB, readability, audio character
QSB period: seconds/minutes
Passband/tuning difficulty: yes/no
Noise floor at each end:
Path bearing and distance:
Space weather / ionosonde clues:
```

Do not collapse those into one number.

### Relevance to NKO reports

This is directly relevant to NKO-style field reports.

If one antenna produces a different mixture of elevation angle, vertical/horizontal field, feedline radiation, common-mode contribution, and polarisation sensitivity, then it may not merely change signal strength. It may change the received path mixture enough to change QSB depth and SSB readability.

That means a report such as:

> “I hear stations with NKO that I could not usefully hear before”

or:

> “The other station hears me steady, but I hear him fading badly”

should not be dismissed as impossible because of reciprocity. Reciprocity is real, but the practical HF channel being sampled by human operators is richer than the slogan.

### References for this section

- University of Toronto, “Lorentz Reciprocity Theorem and Antennas” — explains antenna reciprocity under linear medium assumptions: https://radiance.ece.utoronto.ca/ece1229/notes/reciprocity.pdf
- Purdue University, “Reciprocity Theorem” lecture notes — discusses reciprocity and the relationship between transmit and receive antenna properties: https://engineering.purdue.edu/wcchew/ece604f20/Lecture%20Notes/Lect30.pdf
- ITU-R Recommendation P.533-14, “Method for the prediction of the performance of HF circuits” — states that HF reliability prediction considers signal-to-noise ratio plus expected time and frequency spread of the channel: https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.533-14-201908-I!!PDF-E.pdf
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — notes TID focusing/defocusing and changes to phase, amplitude, polarisation, and angle of arrival; also treats ducting and chordal modes: https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Australian Government / Space Weather Services, “Other Topics — Introduction to HF Radio Propagation” — explains ionospheric tilting, ducting, and chordal modes: https://www.sws.bom.gov.au/Educational/5/2/2
- ITU-R Report P.2011, “Propagation at frequencies above the basic MUF” — lists ducted modes and chordal-hop propagation as mechanisms supporting above-basic-MUF propagation: https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-P.2011-1997-PDF-E.pdf
- Naval Postgraduate School, “Ionospheric Radiowave Propagation” — covers O/X decomposition and Faraday rotation through the ionosphere: https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- Bianchi et al., “Fading in the HF ionospheric channel and the role of irregularities,” *Advances in Space Research*, 2013 — discusses HF fading mechanisms including polarisation, focusing/defocusing, and multipath: https://ionos.ingv.it/Autoscala/pezzopane/2013_AdvancesSpaceResearch_fading.pdf

---

## 14. Travelling ionospheric disturbances, or TIDs

[Previous](#13a-practical-reciprocity-non-reciprocal-qsb-and-what-operators-really-hear) | [Home / Index](#index) | [Next](#15-sporadic-e)

A TID is a travelling ionospheric disturbance: a moving perturbation in ionospheric electron density and layer geometry.

It is tempting to ask whether a TID is “longitudinal” or “magnitude.” The answer is that a TID is not best understood as a simple sound-like longitudinal compression wave. For HF, the important thing is that it produces a travelling change in:

- electron-density magnitude,
- effective layer height,
- slope/tilt of equal-density surfaces,
- refractive index along the path,
- focusing/defocusing,
- delay and Doppler,
- and sometimes scattering/multipath.

Peer-reviewed work in *Annales Geophysicae* describes TIDs as plasma density fluctuations usually driven by atmospheric gravity waves in the neutral atmosphere. TIDs can be driven from above, such as auroral/solar-wind/magnetosphere-ionosphere-thermosphere coupling, or from below, such as tropospheric weather systems launching gravity waves upward.

### TID as an HF ripple

A practical mental model:

```text
smooth-ish F region:      gentle bending surface
TID-disturbed F region:   moving corrugated bending surface
```

A TID can change where your ray returns, how strong it is, and what phase/delay it has. It can focus energy into one area and defocus it from another. It can change skip distance. It can produce QSB, Doppler shift, flutter, or a sudden path improvement.

### TIDs and layer tilts

A tilted or rippled ionosphere can steer rays sideways or change their ground landing point. This means two receiving stations a modest distance apart can experience quite different signal strength and readability.

### TIDs and chordal/ducted modes

Australian SWS notes that ionospheric tilting and disturbances can initiate chordal and ducted modes. These modes may be strong because they can involve fewer D-region crossings and fewer lossy ground reflections.

### TIDs in the Australian context

The Australian region is a good place to care about TIDs because it includes mid-latitude, low-latitude, and equatorial-influenced paths. TIDs can be generated from above by geomagnetic effects and from below by weather-driven gravity waves. Either can change HF propagation without any obvious local weather change at the radio station.

### References for this section

- Prikryl et al., “Observations of traveling ionospheric disturbances driven by gravity waves from sources in the upper and lower atmosphere”, *Annales Geophysicae*, 2025 — https://angeo.copernicus.org/articles/43/511/2025/
- Hocke and Schlegel, “A review of atmospheric gravity waves and travelling ionospheric disturbances: 1982–1995”, *Annales Geophysicae*, 1996 — https://ui.adsabs.harvard.edu/abs/1996AnGeo..14..917H/abstract
- Australian Space Weather Workshop, “Detection and characterisation of travelling ionospheric disturbances” — https://swworkshop.sws.bom.gov.au/presentations/friday/HFAviation/PDF/SWUW_2017_heitmann_slides_v2.pdf
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, discussion of tilting, ducting, chordal modes, and TIDs — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- NASA JPL, “Ionospheric Remote Sensing at JPL”, GNSS-based monitoring of ionospheric acoustic/gravity-wave signatures — https://www.jpl.nasa.gov/go/iono/

---

## 15. Sporadic E

[Previous](#14-travelling-ionospheric-disturbances-or-tids) | [Home / Index](#index) | [Next](#16-transequatorial-propagation-tep-atep-and-etep)

Sporadic E is intense, patchy ionisation in or near the E region. It is not the ordinary smooth E layer simply becoming a little stronger. It can form thin, dense patches that refract or reflect frequencies much higher than ordinary E-region propagation would suggest.

For radio, sporadic E can open paths on 10 m, 6 m, low VHF television/FM frequencies, and sometimes higher VHF. It can appear suddenly, last minutes to hours, move, split, and vanish.

### Distances

Australian SWS states that electron-dense sporadic E can often refract 27 MHz and lower VHF over about 500–1000 nautical miles, roughly 900–1800 km, and is most likely during daytime in summer. ACMA's terrestrial broadcasting technical document says sporadic E can produce signals from transmitters 800–2600 km away at field strengths far above ordinary diffraction expectations.

### Timing

At mid-latitudes, sporadic E is more common in daytime and early evening, and in summer. At high latitudes, it can be tied more to disturbed ionospheric conditions.

### Practical symptoms

Sporadic E can produce:

- sudden strong signals from a sharply defined region,
- stations from one area while nearby areas are absent,
- short-lived openings,
- fast QSB as patches move,
- very high signal strengths,
- interference into services that are normally line-of-sight only.

### Relevance to 10 m and 6 m

For 10 m and 6 m, sporadic E is one of the main explanations for sudden summer openings. It can be strong enough to make the band seem “magically switched on” and then gone again.

### References for this section

- Australian Government / Space Weather Services, “Other Topics — Introduction to HF Radio Propagation”, sporadic E distances and summer/daytime likelihood — https://www.sws.bom.gov.au/Educational/5/2/2
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- ACMA, “Technical Planning Parameters and Methods for Terrestrial Broadcasting”, section on propagation beyond the horizon and sporadic E — https://www.acma.gov.au/sites/default/files/2019-11/Technical%20Planning%20Parameters%20and%20Methods%20for%20Terrestrial%20Broadcasting.pdf
- NASA Scientific Visualization Studio, “Space Weather Effects Animations”, sporadic-E plasma concentrations and radio interference — https://svs.gsfc.nasa.gov/14956/

---

## 16. Transequatorial propagation: TEP, aTEP, and eTEP

[Previous](#15-sporadic-e) | [Home / Index](#index) | [Next](#17-tropospheric-ducting-and-vhfuhf-repeater-openings)

TEP stands for **transequatorial propagation**. It is important on paths crossing the geomagnetic equator, usually roughly north-south. It is not just ordinary F2 propagation with a longer name.

TEP is tied to the equatorial ionosphere, especially:

- the equatorial ionisation anomaly,
- anomaly crests north and south of the magnetic equator,
- field-aligned irregularities,
- equatorial spread F,
- ionospheric tilts,
- and geometry relative to the geomagnetic equator.

The Australian SWS TEP document notes that unusual equatorial propagation can arise from sporadic E, equatorial ionisation enhancements, ionospheric tilts at twilight, and equatorial spread-F irregularities.

### Equatorial ionisation anomaly

The equatorial anomaly has high electron concentration on each side of the magnetic equator, commonly around 10–20 degrees magnetic latitude. It is caused by electric and magnetic-field effects that lift ionised plasma near the magnetic equator; plasma then diffuses along magnetic field lines down toward the anomaly crests.

### aTEP: afternoon transequatorial propagation

**aTEP** is the afternoon form. SWS describes it as a “super F” mode in which a signal is refracted via anomaly crests in opposite hemispheres. It avoids the intermediate ground reflection of a normal 2F mode and passes through the absorbing D region fewer times.

SWS gives aTEP characteristics including:

- MUF up to about 60 MHz,
- often around 1500–1900 local time,
- more common near equinoxes and high sunspot number,
- typical path lengths about 5000–6500 km,
- strong signals with limited fading and distortion compared with eTEP.

### eTEP: evening transequatorial propagation

**eTEP** is the evening form. SWS says it generally supports higher frequencies than aTEP and has rarely been reported even at 432 MHz. It is strongly correlated with range spreading, or equatorial spread F, and is believed to involve ionospheric bubbles, tubes, or plumes.

SWS gives eTEP characteristics including:

- around 2000–2300 local time,
- more common near equinoxes and high sunspot number,
- high signal strengths,
- deep rapid fading,
- strong distortion from multipath and Doppler motion,
- observed Doppler spread up to 2 kHz on CW,
- path lengths about 3000–8000 km,
- possible low-UHF support on rare occasions.

### TEP and one-way impressions

TEP can appear one-way in practice. That does not mean it is a perfect radio diode. It means that useful coupling can differ between directions because of:

- asymmetrical geometry relative to the magnetic equator,
- O/X mode and polarization effects,
- field-aligned irregularities,
- different antenna patterns/noise at each end,
- fading and Doppler spread,
- and rapid path change.

A repeater input can be opened by a distant station even if that station cannot hear the repeater output well enough to know what is happening.

### Relevance to VK3 and VK4

For VK3, 10 m or 6 m paths toward Indonesia, JA, and other north-of-equator regions can involve TEP, especially near equinoxes, high solar activity, and late afternoon/evening timing. For VK4, especially north of Brisbane, the station is closer to low-latitude/equatorial-influenced propagation geometry, so TEP-related effects may show more often on 10 m and 6 m, and may colour 20 m paths toward Asia.

### References for this section

- Australian Government / Space Weather Services, “Transequatorial Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, equatorial anomaly, tilting, chordal modes, and unusual propagation — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Naval Postgraduate School, “Ionospheric Radiowave Propagation”, magnetic-field anisotropy, O/X waves, Faraday rotation — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- NASA, “Our Active Ionosphere”, GOLD mission observations of ionospheric variations — https://svs.gsfc.nasa.gov/5238

---

## 17. Tropospheric ducting and VHF/UHF repeater openings

[Previous](#16-transequatorial-propagation-tep-atep-and-etep) | [Home / Index](#index) | [Next](#18-vk3rhf-style-multi-band-repeater-events-best-propagation-guesses)

Tropospheric ducting is not HF ionospheric propagation. It is lower-atmosphere propagation. It matters mainly at VHF, UHF, and microwave frequencies, although enhanced tropospheric bending can occasionally affect lower VHF.

Ducting occurs when the refractive index of the lower atmosphere changes sharply with height, often due to temperature inversion and humidity structure. A radio wave can be trapped or guided over distances well beyond the normal radio horizon.

ACMA's broadcasting planning document says VHF and UHF waves may propagate well beyond the horizon through ducting and tropospheric scatter, and that flat, coastal, and over-water Australian paths may sometimes produce levels close to free-space propagation for hours.

### Common ducting conditions

Ducting is often associated with:

- stable high-pressure systems,
- temperature inversions,
- warm dry air over cooler moist air,
- coastal/sea paths,
- nocturnal inversion layers,
- and slowly changing weather patterns.

NOAA weather training material explains temperature inversions as situations where temperature increases with height instead of decreasing in the normal way. The radio significance is that this can produce a refractive-index gradient that bends or traps VHF/UHF signals.

### Difference from sporadic E

A quick practical distinction:

```text
Sporadic E: ionospheric, often 10 m / 6 m / low VHF, sudden, patchy, summer daytime/early evening common.
Tropospheric ducting: lower atmosphere, favours VHF/UHF/microwave, often weather/coastal/inversion linked.
```

For a multi-band repeater system, knowing which input opened is essential. The same user experience — “distant stations suddenly hit the repeater” — can have different causes on 10 m, 6 m, and 70 cm.

### References for this section

- ACMA, “Technical Planning Parameters and Methods for Terrestrial Broadcasting”, propagation beyond the radio horizon, ducting, tropospheric scatter, and Australian over-water/coastal paths — https://www.acma.gov.au/sites/default/files/2019-11/Technical%20Planning%20Parameters%20and%20Methods%20for%20Terrestrial%20Broadcasting.pdf
- NIST/NBS, “Commission 2. Tropospheric Radio Propagation” — https://nvlpubs.nist.gov/nistpubs/jres/64D/jresv64Dn6p607_A1b.pdf
- NTIA/ITS, “The Role of Elevated Ducting for Radio Service and Interference Fields” — https://its.ntia.gov/publications/download/81-69_ocr-1.pdf
- NOAA/NWS, “Temperatures — The Inversion” — https://www.weather.gov/source/zhu/ZHU_Training_Page/Miscellaneous/inversion/inversion.html
- Rohde & Schwarz Educational Note, “Understanding VHF Propagation”, useful engineering note but not treated here as a primary authority — https://vertassets.blob.core.windows.net/download/2701f897/2701f897-1433-417e-9b67-405ff698e86d/ha_1101_vhf_educational_note.pdf

---

## 18. VK3RHF-style multi-band repeater events: best propagation guesses

[Previous](#17-tropospheric-ducting-and-vhfuhf-repeater-openings) | [Home / Index](#index) | [Next](#19-vk4-inland-queensland-geography-what-it-may-hint-at)

The conversation raised a real observation: a Mt Dandenong repeater with multiple bands/inputs can suddenly be accessed from a few hundred kilometres-wide area, often 500+ km away, sometimes beyond Sydney; in summer, apparent Indonesian fishing traffic can appear for an hour or two.

The best explanation depends on which input is active.

### If the 70 cm input is active

Best guess: **tropospheric ducting or enhanced tropospheric propagation**.

At 70 cm, ordinary ionospheric return is not a normal explanation. A few hundred to 1000+ km VHF/UHF opening, especially if area-wide and weather/coastal linked, is more likely tropospheric ducting or tropospheric scatter/enhancement.

### If the 6 m input is active

Best guess depends on path and time:

- summer, sudden, 900–2000 km-ish: **sporadic E**,
- north/south equatorial path, late afternoon/evening, high solar/equinox: **TEP/aTEP/eTEP**,
- disturbed conditions: mixed modes possible.

### If the 10 m input is active

Possible mechanisms include:

- ordinary F2,
- sporadic E,
- multi-hop sporadic E,
- TEP/aTEP/eTEP on north-south-ish paths,
- mixed Es/F2 paths.

For Indonesian fishing traffic, 10 m ionospheric propagation is much more likely than 70 cm direct propagation. If the event is late afternoon/early evening and the path crosses the geomagnetic equator suitably, aTEP is a serious candidate. If it is evening with flutter and distortion, eTEP becomes more plausible.

### The key logging item

For any multi-band repeater event, log the input identifier or tail tone first:

```text
Date/time:
Input band identified:
Duration:
Area heard:
Signal character: clean / fluttery / distorted / deep QSB
Weather pattern: inversion / high pressure / coastal duct possibility
Space weather: solar flux, Kp, D-RAP, ionograms
Season and local time:
```

Without input-band identification, the propagation interpretation is ambiguous.

### References for this section

- ACMA, “Technical Planning Parameters and Methods for Terrestrial Broadcasting”, VHF/UHF beyond horizon, ducting/scatter, sporadic E — https://www.acma.gov.au/sites/default/files/2019-11/Technical%20Planning%20Parameters%20and%20Methods%20for%20Terrestrial%20Broadcasting.pdf
- Australian Government / Space Weather Services, “Other Topics — Introduction to HF Radio Propagation”, sporadic E and VHF support — https://www.sws.bom.gov.au/Educational/5/2/2
- Australian Government / Space Weather Services, “Transequatorial Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
- NOAA/NWS, “Temperatures — The Inversion” — https://www.weather.gov/source/zhu/ZHU_Training_Page/Miscellaneous/inversion/inversion.html

---

## 19. VK4 inland Queensland geography: what it may hint at

[Previous](#18-vk3rhf-style-multi-band-repeater-events-best-propagation-guesses) | [Home / Index](#index) | [Next](#20-nko-audioreadability-reports-cautious-propagation-interpretation)

A VK4 tester slightly north of Brisbane and roughly 100 km inland is in a different propagation context from VK3/Melbourne.

### Lower latitude than VK3

The station is closer to low-latitude ionospheric structures and closer to paths that can be influenced by the equatorial anomaly and TEP. This is most directly relevant to 10 m and 6 m, but it can also colour 20 m north/northwest paths toward Indonesia, JA, and Asia.

### Inland, not salt-water coastal

Being inland reduces the chance that excellent reports are simply due to a salt-water coastal vertical enhancement. That does not remove ground effects, but it makes the observation more useful for antenna-pattern and ionospheric-field sampling interpretation.

### Potentially quieter receive site

A station 100 km inland may have a lower man-made noise floor than a dense urban site. If the noise floor is lower, antenna differences and path-quality differences become easier to hear. A quiet receive site can reveal readability improvements that a noisy suburban site hides.

### 40 m and 20 m observations

If the tester reports major differences on both 40 m and 20 m, that is interesting because those bands often sample different propagation regimes:

- 40 m can involve higher-angle regional/interstate paths by day and longer paths at night.
- 20 m is more often medium/low-angle DX, especially into Asia/Pacific and long-haul paths.

If the same antenna system improves practical copy on both bands, the improvement may not be a single simple “low-angle lobe.” It may be a more useful mixture of angle and polarization response under real conditions.

### References for this section

- Australian Government / Space Weather Services, “Transequatorial Radio Propagation”, equatorial anomaly and TEP geometry — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, propagation modes, ionospheric tilting, chordal/ducted modes — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere
- ITU-R Recommendation P.533, antenna performance and HF prediction — https://www.itu.int/rec/R-REC-P.533

---

## 20. NKO audio/readability reports: cautious propagation interpretation

[Previous](#19-vk4-inland-queensland-geography-what-it-may-hint-at) | [Home / Index](#index) | [Next](#21-comparing-antennas-without-fooling-ourselves)

This section treats NKO field reports as observations, not formal proof. The goal is to explain why large readability differences can be physically plausible even when simple gain comparisons do not predict them.

A useful way to present this in a talk is to separate three claims:

1. **Measured/modelled antenna behaviour:** impedance, current distribution, pattern, choke behaviour.
2. **Field observation:** an operator reports better readability, less harsh audio, or more stations copied.
3. **Interpretation:** a proposed reason, such as a better mix of elevation angles, polarization components, or less destructive multipath.

Only the first two are direct observations. The third is a hypothesis until it is supported by repeated tests.

### Report type 1: Q0 to Q4 or better

One report described a signal/readability jump on 29 MHz from effectively unreadable to Q4 or better, with UK, JA, and USA paths mentioned. That is not a minor S-meter difference. It is a change from “speech not recoverable” to “speech quite readable.”

The most plausible propagation interpretation is not simply “more gain.” It is:

> The antenna/path combination changed the received or transmitted mode mixture enough that speech cues became recoverable.

Possible contributors:

- less selective fading across the SSB passband,
- a cleaner dominant path,
- a better polarization mixture,
- less destructive multipath,
- better launch-angle fit to the path,
- or a combination of these.

### Report type 2: “I can hear stations my contact hears”

The VK4 report that NKO hears stations that the contact hears, and that the difference is not minor on 40 m and 20 m, suggests improved station access and copyability rather than only raw strength.

This matters because the receive antenna samples the arriving field. If the arriving field contains several angles and polarizations, an antenna with a more useful mixed response may copy stations that another antenna misses or finds unreadable.

### Report type 3: audio easier for a user with auditory processing difficulty

This is interesting but must be framed carefully. The safe conclusion is:

> A user with an auditory processing difficulty reported that NKO audio was easier to follow. This is a subjective readability observation, not a medical claim.

A plausible radio explanation is that the audio contained more stable speech cues: better SNR, less selective fading, less phase smear, or less listening fatigue from unstable SSB audio.

### Why “readability” can change more than S-meter

The S-meter is a crude indication of received level. It does not directly measure:

- selective fading across the speech passband,
- phase distortion,
- Doppler spread,
- polarization mismatch,
- short-duration fades,
- intelligibility of consonants,
- or listener effort.

A signal can be S7 and unreadable, while another signal can be S5 and easy to copy. SSB readability depends on coherent speech recovery, not merely total RF power at the antenna terminals.

### Cautious NKO hypothesis

A defensible working hypothesis is:

> NKO may improve practical HF copy by changing the mixture of elevation angles, current distribution, and polarization components coupled into and out of the antenna system, thereby changing the multipath and selective-fading mixture presented to the receiver.

This does not claim magic, medical benefit, or guaranteed gain. It says the antenna may be sampling or launching a more useful part of the real ionospheric field.

### What would strengthen the case

Stronger evidence would include:

- rapid A/B/A/B comparisons under the same path conditions,
- recordings of both antennas,
- waterfall/audio spectrum comparisons,
- SNR and intelligibility scoring,
- reports from multiple receivers at different locations,
- logging ionospheric context: foF2, MUF estimates, D-RAP, Kp, solar flux, time, path bearing,
- noting whether the change is level, readability, distortion, or all three.

### References for this section

- ITU-R Recommendation P.533, scope includes signal-to-noise, time spread, and frequency spread in HF circuit performance — https://www.itu.int/rec/R-REC-P.533
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, multi-mode propagation, tilting, ducting, chordal modes — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Naval Postgraduate School, “Ionospheric Radiowave Propagation”, O/X modes and Faraday rotation — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- U.S. National Institute on Deafness and Other Communication Disorders, “Auditory Processing Disorder” — https://www.nidcd.nih.gov/health/auditory-processing-disorder
- NOAA NCEI, “Sudden Ionospheric Disturbances Data”, HF frequency deviations — https://www.ngdc.noaa.gov/stp/solar/sid.html

---

## 21. Comparing antennas without fooling ourselves

[Previous](#20-nko-audioreadability-reports-cautious-propagation-interpretation) | [Home / Index](#index) | [Next](#22-practical-indicators-to-watch)

HF antenna comparison is useful, but easy to fool ourselves with. QSB, selective fading, local noise, AGC action, and operator expectation can all make a casual A/B test look more certain than it really is.

The aim is not to prove a favourite antenna is always better. The aim is to collect observations that are hard to dismiss.

### First rule

Do not test only:

```text
A → B
```

Use at least:

```text
A → B → A
```

Better:

```text
A → B → A → B → A → B
```

If A was good, then B was poor, then A was also poor when you went back, you probably measured QSB rather than antenna performance.

### What to compare

Do not ask only, “Which is stronger?”

Ask separately:

- Which is stronger?
- Which has the better signal-to-noise ratio?
- Which is easier to understand?
- Which has less QSB?
- Which sounds less phasey, hollow, watery, muffled, or harsh?
- Which would you choose for a marginal contact?

For SSB, the last question may be the most useful.

### Practical methods

| Method | Good for | Main trap | Practical comment |
|---|---|---|---|
| **Manual A/B during a QSO** | Quick real-world reports | QSB and politeness bias | Always return to A. Ask for readability and audio quality, not just S-points. |
| **Receive-only A/B at your station** | Hearing noise and audio differences yourself | Memory bias and AGC masking | Record the audio if possible. Listening later is often more honest. |
| **Fast relay A/B switching** | Reducing QSB error | Relay wiring, isolation, AGC settling | 10–20 seconds per antenna is often enough for SSB speech without waiting too long. |
| **Two receivers or two SDR channels** | Best receive comparison | Gain calibration and antenna coupling | This is the cleanest way to see whether one antenna fades while the other does not. |
| **WSPR / RBN / skimmers** | Long-term signal statistics | Narrowband digital is not SSB readability | Excellent for reach and SNR trends; not enough by itself for voice quality claims. |
| **Many field reports** | Real amateur use | Folklore and uncontrolled conditions | Valuable if reports are structured and repeated. Weak if they are only “it was better.” |

### Minimum useful log

For any serious comparison, write down:

```text
Date/time UTC:
Band/frequency:
Mode:
Power:
Antenna A:
Antenna B:
Switching pattern: A/B, A/B/A, or A/B/A/B
Remote station/location:
Path direction and approximate distance:
S-meter or measured level A:
S-meter or measured level B:
Noise level A/B:
Readability A/B:
QSB A/B:
Audio comments:
Was a recording made?
Propagation notes: day/night path, solar flare/D-RAP, Kp, foF2/MUF if known
```

### Watch these traps

- **One switch is not a test.** A/B alone can be pure QSB.
- **S-meter is not readability.** A weaker signal can be easier to copy.
- **Noise matters.** The better receive antenna may be the quieter one, not the louder one.
- **AGC hides differences.** The receiver may make two signals sound closer in level than they really are.
- **Antennas interact.** Nearby wires, masts, fences, gutters, and unused antennas can become part of the test.
- **Feedline current matters.** Decide whether feedline current is accidental or part of the design.
- **One path is not all paths.** An antenna can win on 40 m local/interstate and lose on 20 m DX, or the reverse.
- **Do not average away readability.** A station may be readable because the audio is cleaner, not because the total RF power is higher.

### For NKO comparisons

NKO reports should separate three things:

1. **Strength:** S-meter or measured level.
2. **Noise/SNR:** whether the wanted signal is clearer above the noise.
3. **Readability:** whether speech is easier to copy.

The most interesting NKO reports are not just “it was louder.” They are reports such as:

- “I could copy it now.”
- “The signal was easier to tune.”
- “The audio was cleaner.”
- “The other antenna was stronger but harder to understand.”
- “NKO heard stations the comparison antenna missed.”

Those are worth collecting, but they need careful logging. A fair NKO comparison should say:

> Under these conditions, on this path, at this time, NKO was more readable than the comparison antenna.

That is stronger and more honest than claiming universal gain.

### Best simple test

For most amateurs, the best practical test is:

```text
A/B/A/B switching + audio recording + written notes
```

Repeat it on several bands, paths, and days. One test is an observation. A repeated pattern becomes evidence.

### References for this section

- ITU-R Recommendation P.533, HF prediction includes antenna characteristics, signal-to-noise, reliability, time spread, and frequency spread — https://www.itu.int/rec/R-REC-P.533
- Australian Government / Space Weather Services, ASAPS documentation, fading and multiple modes — https://www.sws.bom.gov.au/Category/Products%20and%20Services/Software/ASAPS/ASAPSVer5.3.pdf
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation”, antenna pattern as one factor among path mechanisms — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- NOAA Space Weather Prediction Center, “HF Radio Communications”, space-weather impacts on HF circuits — https://www.swpc.noaa.gov/impacts/hf-radio-communications

---

## 22. Practical indicators to watch

[Previous](#21-comparing-antennas-without-fooling-ourselves) | [Home / Index](#index) | [Next](#23-what-is-solid-what-is-plausible-and-what-still-needs-testing)

No single indicator explains HF. Use several.

### foF2 maps and ionograms

foF2 tells you the vertical F2 critical frequency. It is especially helpful for NVIS and lower-HF support. If foF2 is below 7 MHz, 40 m high-angle local paths may struggle. If foF2 rises above 7 MHz, 40 m can become strong for shorter paths. For oblique paths, MUF can be much higher than foF2.

Ionograms reveal more than a single number. They can show E, F1, F2, sporadic E, spread F, missing traces, and disturbed conditions.

### D-RAP and solar flares

D-RAP is useful when daytime absorption suddenly worsens, especially during solar X-ray flares or polar cap absorption events. If lower HF suddenly disappears on the sunlit side, check D-RAP and X-ray flare status.

### Kp and geomagnetic activity

Kp is a broad geomagnetic index. High Kp can indicate disturbed conditions, but it is not a perfect predictor for every HF path. Some paths degrade; some shift; some unusual modes appear. Quiet conditions can also allow equatorial irregularities related to eTEP.

### Time of day and daylight path

For absorption, ask: how much of the path is sunlit, and how many D-region crossings are involved?

For F-region support, ask: where are the reflection/control points, and what is the local solar time there?

### Season

- Summer mid-latitudes: more sporadic E.
- Equinox: often important for TEP and many F-region long paths.
- Winter: less D absorption, different F2 chemistry/transport behaviour.

### Path bearing

A path crossing the geomagnetic equator roughly north-south is a TEP candidate on higher HF/lower VHF. A coastal VHF/UHF path under stable weather is a ducting candidate. A short daytime 40 m path is likely ordinary F-region/NVIS-like support if foF2 allows.

### Signal character

The sound tells you something:

```text
slow rolling fades: ordinary multipath/QSB
watery SSB: selective fading/phase smear
fluttery CW/SSB: Doppler spread/disturbed path/TEP/eTEP/auroral-like effects
sudden strong summer 10 m/6 m opening: consider sporadic E
strong late-afternoon north-south 6 m/10 m: consider aTEP
strong evening distorted north-south VHF: consider eTEP
UHF repeater from 500+ km: consider tropo ducting first
```

### References for this section

- Australian Government / Space Weather Services, “Global HF — Ionospheric Map” — https://www.sws.bom.gov.au/HF_Systems/6/5
- NOAA NCEI, “Vertical Incidence Soundings (Ionograms)” — https://www.ngdc.noaa.gov/stp/IONO/ionogram.html
- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- NOAA Space Weather Prediction Center, “Solar Flares (Radio Blackouts)” — https://www.swpc.noaa.gov/phenomena/solar-flares-radio-blackouts
- Australian Government / Space Weather Services, “Transequatorial Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
- ACMA, “Technical Planning Parameters and Methods for Terrestrial Broadcasting” — https://www.acma.gov.au/sites/default/files/2019-11/Technical%20Planning%20Parameters%20and%20Methods%20for%20Terrestrial%20Broadcasting.pdf

---

## 23. What is solid, what is plausible, and what still needs testing

[Previous](#22-practical-indicators-to-watch) | [Home / Index](#index) | [Next](#24-consolidated-source-list)

### Solid

These points are well supported by government/academic/standards sources:

- The ionosphere modifies and refracts radio waves.
- D, E, F1, and F2 are broad regions, not hard mirrors.
- D-region absorption is collision-related and can be severe for HF, especially during solar flares.
- The F2 region is central to long-distance HF support.
- The geomagnetic field makes the ionosphere anisotropic.
- O and X magneto-ionic modes exist.
- Faraday rotation changes polarization through the ionosphere.
- Antenna reciprocity is real for passive linear antennas, but practical HF fading/readability reports need not be reciprocal because the channel is time-varying, multipath, polarisation-changing, and locally noisy.
- HF paths can have time and frequency spread, which affects reliability and intelligibility.
- TIDs are travelling plasma-density disturbances often driven by atmospheric gravity waves.
- Sporadic E can support high HF/lower VHF over 900–2000 km-ish paths.
- aTEP and eTEP have different timing, frequency support, distortion, and geometry.
- VHF/UHF signals can propagate beyond the radio horizon through tropospheric ducting/scatter.
- NEC-style modelling is a strong design tool for antenna currents, impedance, and idealised patterns, but it is not a complete model of real HF readability through a changing ionosphere.

### Plausible

These are plausible interpretations of field observations:

- NKO may improve readability more than raw S-meter strength by changing the mix of launch angles and polarization components.
- NKO may sometimes provide a cleaner dominant path or reduce destructive multipath in SSB.
- A listener with auditory processing difficulty may find cleaner/more stable SSB audio easier to follow.
- VK4 inland location may make real antenna differences easier to hear because of lower noise and different low-latitude path geometry.
- VK3RHF Indonesian fishing traffic is likely 10 m/6 m ionospheric propagation if the relevant input is on those bands; 70 cm direct ionospheric propagation is unlikely except for rare/exceptional mechanisms and should first be checked for other explanations.

### Needs testing

These need controlled evidence before strong claims:

- NKO gives a fixed dB gain advantage over a comparison antenna.
- NKO consistently reduces selective fading across all paths.
- NKO is generally better for all listeners and all conditions.
- A NEC model by itself proves real-world readability advantage without field measurements.
- Faraday rotation alone explains one-way contacts.
- A specific repeater event was definitely aTEP/eTEP/Es/tropo without input identification and timing data.

### Practical conclusion

The most defensible NKO propagation claim is not “huge gain.” It is:

> NKO may improve practical copyability by changing the useful mix of fields coupled into and out of the antenna system under real ionospheric conditions.

That is worth investigating because HF copyability is affected by multipath, polarization, O/X mode behaviour, selective fading, and listener speech recovery — not just antenna gain.

### References for this section

- ITU-R Recommendation P.533 — https://www.itu.int/rec/R-REC-P.533
- NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere
- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- Australian Government / Space Weather Services, “Transequatorial Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
- Naval Postgraduate School, “Ionospheric Radiowave Propagation” — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
- Prikryl et al., *Annales Geophysicae*, 2025 — https://angeo.copernicus.org/articles/43/511/2025/
- ACMA, “Technical Planning Parameters and Methods for Terrestrial Broadcasting” — https://www.acma.gov.au/sites/default/files/2019-11/Technical%20Planning%20Parameters%20and%20Methods%20for%20Terrestrial%20Broadcasting.pdf

---

## 24. Consolidated source list

[Previous](#23-what-is-solid-what-is-plausible-and-what-still-needs-testing) | [Home / Index](#index) | [Next](#25-glossary)

This source list is included for convenience. Each major section above also has its own local references.

### Government and standards

1. NOAA Space Weather Prediction Center, “Ionosphere” — https://www.swpc.noaa.gov/phenomena/ionosphere
2. NOAA Space Weather Prediction Center, “HF Radio Communications” — https://www.swpc.noaa.gov/impacts/hf-radio-communications
3. NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
4. NOAA Space Weather Prediction Center, “Solar Flares (Radio Blackouts)” — https://www.swpc.noaa.gov/phenomena/solar-flares-radio-blackouts
5. NOAA Space Weather Prediction Center, “Solar Radiation Storm” — https://www.swpc.noaa.gov/phenomena/solar-radiation-storm
6. NOAA Space Weather Prediction Center, “STORM Time Empirical Ionospheric Correction” — https://www.swpc.noaa.gov/products/storm-time-empirical-ionospheric-correction
7. NOAA NCEI, “Definition of the Ionospheric Regions (Structures)” — https://www.ngdc.noaa.gov/stp/IONO/ionostru.html
8. NOAA NCEI, “Vertical Incidence Soundings (Ionograms)” — https://www.ngdc.noaa.gov/stp/IONO/ionogram.html
9. NOAA NCEI, “Sudden Ionospheric Disturbances Data” — https://www.ngdc.noaa.gov/stp/solar/sid.html
10. Australian Government / Space Weather Services, “Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
11. Australian Government / Space Weather Services, “Other Topics — Introduction to HF Radio Propagation” — https://www.sws.bom.gov.au/Educational/5/2/2
12. Australian Government / Space Weather Services, “Global HF — Ionospheric Map” — https://www.sws.bom.gov.au/HF_Systems/6/5
13. Australian Government / Space Weather Services, “Transequatorial Radio Propagation” — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Transequatorial.pdf
14. Australian Government / Space Weather Services, “ASAPS Version 5.3 Tutorial” — https://www.sws.bom.gov.au/Category/Products%20and%20Services/Software/ASAPS/ASAPSVer5.3.pdf
15. ACMA, “Technical Planning Parameters and Methods for Terrestrial Broadcasting” — https://www.acma.gov.au/sites/default/files/2019-11/Technical%20Planning%20Parameters%20and%20Methods%20for%20Terrestrial%20Broadcasting.pdf
16. ITU-R Recommendation P.533, “Method for the prediction of the performance of HF circuits” — https://www.itu.int/rec/R-REC-P.533
17. ITU-R Recommendation P.1240, “ITU-R methods of basic MUF, operational MUF and ray-path prediction” — https://www.itu.int/rec/R-REC-P.1240
18. NTIA/ITS, “The Role of Elevated Ducting for Radio Service and Interference Fields” — https://its.ntia.gov/publications/download/81-69_ocr-1.pdf
19. NOAA/NWS, “Temperatures — The Inversion” — https://www.weather.gov/source/zhu/ZHU_Training_Page/Miscellaneous/inversion/inversion.html
20. U.S. National Institute on Deafness and Other Communication Disorders, “Auditory Processing Disorder” — https://www.nidcd.nih.gov/health/auditory-processing-disorder

### Academic, university, and research sources

1. Naval Postgraduate School, “Ionospheric Radiowave Propagation” — https://faculty.nps.edu/jenn/EC3630/Ionosphere%28v1.6.5%29.pdf
2. National Bureau of Standards / NIST legacy publication, “Ionospheric Radio Propagation” — https://nvlpubs.nist.gov/nistpubs/Legacy/circ/nbscircular462.pdf
3. Prikryl et al., “Observations of traveling ionospheric disturbances driven by gravity waves from sources in the upper and lower atmosphere”, *Annales Geophysicae*, 2025 — https://angeo.copernicus.org/articles/43/511/2025/
4. Hocke and Schlegel, “A review of atmospheric gravity waves and travelling ionospheric disturbances: 1982–1995”, *Annales Geophysicae*, 1996 — https://ui.adsabs.harvard.edu/abs/1996AnGeo..14..917H/abstract
5. NASA NTRS, H. Unz, “Ionospheric Effects on 400 Mc Radar Signals” — https://ntrs.nasa.gov/api/citations/19670002948/downloads/19670002948.pdf
6. CEDAR, “Radio Waves in the Ionosphere” — https://cedarscience.org/sites/default/files/meeting/Miller_CEDAR.pdf
7. UCAR Center for Science Education, “The Ionosphere” — https://scied.ucar.edu/learning-zone/atmosphere/ionosphere
8. UCAR Heliophysics, “Ionosphere and Thermosphere Basics” — https://heliophysics.ucar.edu/sites/default/files/heliophysics/resources/presentations/2021-HelioSS-Zou-Ionosphere-Basics-Dynamics.pdf
9. NASA, “10 Things to Know About the Ionosphere” — https://science.nasa.gov/earth/10-things-to-know-about-the-ionosphere/
10. NASA Scientific Visualization Studio, “Our Active Ionosphere” — https://svs.gsfc.nasa.gov/5238
11. NASA Scientific Visualization Studio, “Radio Signal Reflection & Refraction on a Simple Ionosphere Model” — https://svs.gsfc.nasa.gov/5240/
12. NASA Scientific Visualization Studio, “Space Weather Effects Animations” — https://svs.gsfc.nasa.gov/14956/
13. NASA JPL, “Ionospheric Remote Sensing at JPL” — https://www.jpl.nasa.gov/go/iono/

---


Additional sources added for gray-line, space weather, solar noise, and receiver hiss:

- Australian Government / Space Weather Services, “Digital HF Prediction Tool Help” — https://www.sws.bom.gov.au/Category/HF%20Systems/Online%20Tools/Prediction%20Tools/DigitalHF/help.php
- Lo, S.; et al., “A Systematic Study of 7 MHz Greyline Propagation Using Amateur Radio Beacon Signals,” *Atmosphere*, 2022 — https://www.mdpi.com/2073-4433/13/8/1340
- Cameron, T. G.; et al., “High-Latitude Off-Great Circle Propagation Associated With Large-Scale Ionospheric Gradients Along the Solar Terminator,” *Radio Science*, 2024 — https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2023RS007917
- NASA/NOAA, “Sun Reaches Maximum Phase in 11-Year Solar Cycle” — https://science.nasa.gov/science-research/heliophysics/nasa-noaa-sun-reaches-maximum-phase-in-11-year-solar-cycle/
- NOAA Space Weather Prediction Center, “Solar Cycle Progression” — https://www.swpc.noaa.gov/products/solar-cycle-progression
- NOAA Space Weather Prediction Center, “NOAA Space Weather Scales” — https://www.swpc.noaa.gov/noaa-scales-explanation
- NOAA Space Weather Prediction Center, “Solar Flares (Radio Blackouts)” — https://www.swpc.noaa.gov/phenomena/solar-flares-radio-blackouts
- NOAA Space Weather Prediction Center, “D Region Absorption Predictions (D-RAP)” — https://www.swpc.noaa.gov/products/d-region-absorption-predictions-d-rap
- NOAA NCEI, “Solar Radio Datasets” — https://www.ncei.noaa.gov/products/space-weather/legacy-data/solar-radio-datasets
- NOAA Space Weather Prediction Center, “Space Weather Glossary” — https://www.swpc.noaa.gov/content/space-weather-glossary
- ITU-R Recommendation P.372, “Radio noise” — https://www.itu.int/rec/R-REC-P.372
- Pederick, L. H.; Cervera, M. A., “A directional HF noise model: Calibration and validation in the Australian region,” *Radio Science*, 2016 — https://www.dst.defence.gov.au/sites/default/files/basic_pages/documents/2016%20Pederick%20and%20Cervera%20-%20SPINE%20Noise.pdf
- Landecker, T. L.; et al., “A survey of the polarized emission from the Galactic plane at 1420 MHz with arcminute angular resolution,” *Astronomy & Astrophysics*, 2010 — https://www.aanda.org/articles/aa/pdf/2010/12/aa13921-09.pdf

Additional sources added for ducted and chordal modes:

- Australian Government / Space Weather Services, “Introduction to HF Radio Propagation,” section 2.4 on propagation modes, ducting, and chordal modes — https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro_HF_Radio.pdf
- ITU-R Report P.2011, “Propagation at frequencies above the basic MUF” — https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-P.2011-1997-PDF-E.pdf
- ITU-R Recommendation P.531-15, “Ionospheric propagation data and prediction methods required for the design of satellite networks and systems” — https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.531-15-202308-S!!PDF-E.pdf
- Platt, I. G., “MF and HF propagation characteristics of ionospheric ducts,” *Journal of Atmospheric and Terrestrial Physics*, 1989 — https://www.sciencedirect.com/science/article/pii/0021916989900330
- Carrara, N., “Guided Propagation of HF Radio Waves in the Ionosphere,” *Space Science Reviews*, 1970 — https://adsabs.harvard.edu/full/1970SSRv...11..555C


Additional sources added for practical reciprocity and non-reciprocal QSB:

- University of Toronto, “Lorentz Reciprocity Theorem and Antennas” — https://radiance.ece.utoronto.ca/ece1229/notes/reciprocity.pdf
- Purdue University, “Reciprocity Theorem” lecture notes — https://engineering.purdue.edu/wcchew/ece604f20/Lecture%20Notes/Lect30.pdf
- ITU-R Recommendation P.533-14, “Method for the prediction of the performance of HF circuits” — https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.533-14-201908-I!!PDF-E.pdf
- Bianchi et al., “Fading in the HF ionospheric channel and the role of irregularities,” *Advances in Space Research*, 2013 — https://ionos.ingv.it/Autoscala/pezzopane/2013_AdvancesSpaceResearch_fading.pdf
- Zhou et al., “Midlatitude ionospheric HF channel reciprocity: Evidence from ionospheric oblique incidence sounding experiments,” *Radio Science*, 2010 — https://doi.org/10.1029/2010RS004476

Additional sources added for NEC modelling and antenna-model limits:

- Burke and Poggio, *Numerical Electromagnetics Code (NEC) — Method of Moments*, Part III User’s Guide — https://www.nec2.org/other/nec2prt3.pdf
- Burke, “Ground Model Options in the NEC-4.2 Antenna Code,” Lawrence Livermore / OSTI — https://www.osti.gov/servlets/purl/1117909

## 25. Glossary

[Previous](#24-consolidated-source-list) | [Home / Index](#index) | [Next](#index)

**Atmospheric noise** — Radio noise mainly produced by lightning and related atmospheric electrical activity. On HF it can arrive from distant storm regions by skywave paths.

**Continuum storm** — NOAA term for solar radio noise lasting hours and sometimes days, with intensity varying smoothly over a wide frequency range in the meter and decimeter wavelengths.

**D-RAP** — NOAA/SWPC D-Region Absorption Prediction product. It estimates HF absorption effects from solar X-ray flux and solar energetic protons.

**F10.7** — Solar radio flux at 10.7 cm wavelength, often used as a proxy for solar EUV activity and general solar-cycle state.

**Galactic noise** — External radio noise from the Milky Way and other cosmic sources. At quiet HF sites it can become important, especially at higher HF and at night.

**Gray-line / grey-line propagation** — HF propagation enhancement or unusual propagation near the day-night terminator, commonly associated with reduced D-region absorption, persistent F-region ionisation, and terminator gradients.

**Kp index** — A planetary geomagnetic index used as a broad indicator of geomagnetic disturbance. Useful as a clue, but not a complete HF path prediction.

**Man-made noise** — Radio noise from human electrical/electronic systems such as power supplies, solar inverters, lighting, power lines, chargers, motors, and data services.


**NEC modelling caveat** — NEC-style antenna modelling is highly useful for currents, impedance, and idealised radiation patterns, but it does not by itself predict ionospheric readability, QSB, selective fading, local noise, or listener speech recovery. For NKO, a model should be treated as design evidence, not final proof of field performance.

**NKO field report caveat** — An NKO field report is an operator observation unless it is backed by controlled A/B testing, recordings, and logged propagation context. Reports of better audio or readability are valuable, but should be presented as observations and hypotheses, not guaranteed performance claims.

**Noise floor** — The background noise level at the receiver. Signals below or close to this level are hard or impossible to copy.

**Non-reciprocal QSB** — Practical operating situation where one station hears strong fading while the other station does not hear comparable fading on the return signal. It can result from non-simultaneous overs, different antennas, different polarisation coupling, different multipath mixtures, TIDs, ducting/chordal-mode coupling, and different local noise floors.

**Practical reciprocity** — The operator-level question of whether two stations experience the same strength, fading, and readability. This is weaker and messier than formal antenna or electromagnetic reciprocity.

**Reciprocity** — In antenna theory, the principle that a passive linear antenna has related transmit and receive properties under the same conditions. In HF operation this does not guarantee equal reports, equal QSB, or equal readability at both ends of a QSO.

**Radio blackout** — NOAA R-scale event where flare-produced X-ray/EUV radiation enhances the D region on the sunlit side, causing HF degradation or absorption.

**Solar cycle** — The roughly 11-year cycle of solar magnetic activity, tracked by sunspots and solar flux. It strongly affects ionospheric density and HF propagation.

**Solar maximum** — The active part of the solar cycle, with more sunspots, higher solar flux, more upper-HF openings, and greater chance of flares and storms.

**Solar minimum** — The quieter part of the solar cycle, with fewer sunspots and fewer high-MUF openings, but often more geomagnetically quiet days.

**Solar radio burst** — A burst of radio emission from the Sun, often associated with flares. It can directly raise received noise or interfere with radio systems.

**Solar radiation storm** — An event involving energetic solar protons. These can enhance D-region absorption at high latitudes and cause polar cap absorption.

**Solar terminator** — The moving boundary between sunlit and dark parts of Earth’s atmosphere/ionosphere.


### Above-basic-MUF propagation

Propagation that occurs at frequencies higher than the basic MUF expected for a simple predicted path. ITU-R P.2011 lists mechanisms such as ionospheric roughness, ducted modes, chordal-hop propagation, scatter, sporadic E, auroral scatter, and meteor scatter.

### aTEP

Afternoon transequatorial propagation. A TEP mode typically occurring late afternoon to early evening, often near equinoxes and high sunspot numbers, with strong signals and relatively limited distortion compared with eTEP.

### Absorption

Loss of RF energy in the ionosphere. In the D region, this is mainly collision loss: electrons moved by the RF field collide with neutral particles and turn organised RF energy into heat.

### Anisotropic medium

A medium whose properties depend on direction. The magnetised ionosphere is anisotropic because the Earth's magnetic field gives it a preferred direction.

### APD

Auditory processing disorder. Included here only because one NKO listener report involved auditory processing difficulty. It is not an RF propagation mechanism, and no antenna medical claim should be made.

### Appleton-Hartree equation

A magneto-ionic formula for the refractive index of a radio wave in a magnetised plasma. It predicts two propagation modes, corresponding broadly to ordinary and extraordinary waves.

### Chordal mode

A propagation mode involving multiple ionospheric refractions without intermediate ground reflections. It can be strong because it avoids some D-region crossings and ground losses. In many practical discussions this is called chordal-hop propagation.

### Ducted mode

A propagation mode where the wave is partly guided or trapped within an ionospheric structure, somewhat like a temporary leaky waveguide. It can support long ranges or above-basic-MUF propagation when the electron-density profile and launch angle are favourable.

### Critical frequency

The highest frequency returned by an ionospheric layer at vertical incidence. For the F2 layer this is foF2.

### D region

Low ionospheric region mainly important for absorption. It is strongest during daylight and can become highly absorbing during solar flares or particle events.

### D-RAP

NOAA SWPC D Region Absorption Prediction product. It estimates HF absorption impact from solar X-rays and solar energetic particles.

### eTEP

Evening transequatorial propagation. Often associated with equatorial spread F and field-aligned irregularities. It can support high frequencies but may have deep rapid fading and strong distortion.

### E region

Ionospheric region above D and below F. It can refract lower HF and can host sporadic E patches.

### Equatorial ionisation anomaly

Two enhanced electron-density crests on either side of the magnetic equator, produced by electric and magnetic-field-driven plasma motion and diffusion along magnetic field lines.

### Es

Sporadic E. Thin, dense, patchy E-region ionisation capable of refracting frequencies much higher than the regular E layer.

### Extraordinary wave

The X-mode. One of the two natural propagation modes in the magnetised ionosphere. It is more strongly influenced by the Earth's magnetic field.

### F1 region

Daytime F-region shoulder or sub-layer below F2. Often merges into the broader F region at night.

### F2 region

Main HF long-distance refracting region. Often has the highest electron density and is central to foF2 and MUF behaviour.

### Faraday rotation

Rotation of the polarization plane of a wave passing through a magnetised plasma. In the ionosphere it is caused by different phase advance of the natural magneto-ionic components.

### Flutter

Rapid amplitude/phase variation, often heard as a rough or trembling signal. It can be caused by Doppler spread, disturbed ionosphere, auroral effects, eTEP, or rapidly changing multipath.

### foF2

Ordinary-wave F2 critical frequency. The highest frequency reflected vertically by the F2 region on an ionogram.

### Frequency spread

A widening of received signal frequency due to Doppler shifts and multipath. Important in HF channel performance and especially harmful to narrow modes or clean SSB/CW copy.

### Ground reflection

Reflection from land or sea between ionospheric hops. Sea reflection can be strong; lossy ground can reduce signal and alter phase/polarization.

### HF

High Frequency, usually 3–30 MHz.

### Ionogram

A plot from an ionosonde showing echo return time/virtual height versus frequency. It reveals ionospheric layers, critical frequencies, sporadic E, spread F, and disturbances.

### Ionosonde

A radar-like sounder that transmits swept HF pulses vertically or obliquely to measure ionospheric reflection characteristics.

### Ionosphere

Ionised part of the upper atmosphere that modifies radio waves. It is produced mainly by solar EUV and X-ray radiation and is structured by chemistry, density, winds, electric fields, and the geomagnetic field.

### LUF

Lowest usable frequency. The lower frequency limit for a useful path, usually set by absorption and noise.

### Magnetised plasma

A plasma threaded by a magnetic field. The ionosphere is a magnetised plasma, so wave behaviour depends on the Earth's magnetic field.

### Magneto-ionic mode

A natural propagation mode of a radio wave in a magnetised ionised medium. The O and X waves are magneto-ionic modes.

### MUF

Maximum usable frequency. The highest frequency expected to support a specific path at a specific time.

### Multipath

Reception of several versions of the same signal via different paths, delays, phases, and polarizations.

### NVIS

Near Vertical Incidence Skywave. High-angle HF propagation used for short to medium paths, often on 80 m and 40 m depending on foF2 and absorption.

### Ordinary wave

The O-mode. One of the two natural propagation modes in the magnetised ionosphere. It is the mode commonly scaled as foF2 on ionograms.

### OWF

Optimum working frequency. A frequency chosen below the MUF for better reliability.

### Polar cap absorption

HF absorption in polar regions caused by energetic particles increasing lower-ionosphere ionisation.

### Polarization

Orientation and time behaviour of the electric field. HF polarization can rotate or become elliptical after ionospheric propagation.

### QSB

Fading. The received signal rises and falls because of changing path loss and vector addition/cancellation of multipath components.

### Readability

How easily speech can be copied. Readability is not the same as S-meter strength; it depends on SNR, fading, distortion, passband shape, and listener recovery of speech cues.

### Refraction

Gradual bending of a radio wave due to changing refractive index. Most HF “reflection” from the ionosphere is better understood as refraction.

### Selective fading

Fading that affects different parts of a signal bandwidth differently. In SSB it can damage speech clarity even when the total signal level remains high.

### SID

Sudden ionospheric disturbance. A rapid ionospheric change often caused by solar flare radiation, which can affect HF propagation and cause radio blackouts or frequency deviations.

### Skip distance

The distance from the transmitter to the first return point of a skywave signal, leaving a possible zone of weak or absent coverage closer in.

### Sporadic E

See Es.

### Spread F

Ionogram spreading of the F-region trace, usually indicating ionospheric irregularities. Important in eTEP and equatorial irregularity discussions.

### TEP

Transequatorial propagation. Propagation across the geomagnetic equator, often using equatorial anomaly structures and field-aligned irregularities.

### TID

Travelling ionospheric disturbance. A moving perturbation in ionospheric electron density and shape, usually driven by atmospheric gravity waves or space-weather coupling.

### Time spread

Spread in arrival times of multipath components. In HF, time spread can damage digital modes and can contribute to SSB smearing.

### Tropospheric ducting

VHF/UHF/microwave propagation beyond the normal radio horizon due to lower-atmosphere refractive-index structure, often associated with temperature inversions and humidity gradients.

### X-mode

Extraordinary wave. The magneto-ionic mode more strongly shaped by the Earth's magnetic field.

