# NKO Antenna: Mechanisms, Observations, and Performance Implications

## Summary

The NKO is not just a conventional OCF with a different transformer. It also differs materially from the commonly documented New Carolina Windom.

It is best understood as a three-conductor antenna system:

- the apex uses a 4:1 **UnUn** rather than a conventional balanced feed arrangement
- the outside of the coax shield above the lower 1:1 current balun is an intended part of the antenna
- that defined vertical section is fed from the top and contributes as a top-fed vertical radiator
- the horizontal arms and vertical section form one coupled antenna, not two complete antennas simply added together
- the resulting current distribution, polarisation response, pattern and on-air behaviour can differ from a conventional OCF or EFHW
- field comparisons indicate stronger signals and improved intelligibility on some paths, although not as a guaranteed advantage on every path

The vertical section is elevated and does not depend on a ground-mounted radial system, but it is not independent of the earth. Its pattern and loss are still influenced by height, soil and the rest of the connected antenna structure.

The purpose of this document is to summarise the main working explanation for the behaviour observed so far.

---

## 1. The 4:1 UnUn At The Apex

The NKO uses a **4:1 UnUn** at the apex, and that choice is **fundamental** to the antenna.

A conventional OCF antenna has unequal arms and unequal feedpoint impedances on each side.

- A well-designed 4:1 current balun can still feed an OCF successfully, but the balun does not make the antenna itself symmetrical. It transforms impedance, and it also attempts to limit unwanted current on the outside of the feedline.
- A 4:1 voltage balun also transforms impedance, but generally provides less direct control of common-mode feedline current when the load is asymmetric. The shield of the coax will be driven as a result of imbalance between the OCF arms.

_The NKO takes a different approach._ The 4:1 UnUn transforms impedance while directly connecting the outside of the coax shield to the short-side feedpoint. This allows significant current to flow on the shield down to the lower 1:1 current balun, making that section an intentional conductor and radiator rather than an accidental extension of the feedline.

The short arm and shield are driven from the same feedpoint terminal. That gives them a defined starting relationship, but it should not be taken to mean that their currents remain equal or exactly in phase along their full lengths. Current magnitude and phase vary along all three conductors and change by band.

The practical distinction is:

- in a conventional OCF, outside-shield current is normally something the feed system tries to suppress
- in the NKO, outside-shield current above the lower 1:1 current balun is deliberately allowed and used
- the lower 1:1 current balun then defines where that radiating section should substantially end

This changes the current division at the apex and may bring the short side and long side into a more useful relationship than the two wire arms would otherwise achieve alone.

It is more accurate, however, to describe this as a redistribution of current through one coupled antenna than as shield current simply being “added” to the short arm.

Whether the NKO arrangement reduces loss or stress in the 4:1 UnUn remains an open engineering question. Core stress depends on the actual terminal voltage and current, the reactive part of the load, frequency, winding arrangement and core loss. Improved current distribution may help, but it cannot be assumed from balance alone and should be confirmed by temperature, current and voltage measurements.

## How the NKO changes by band

Because the vertical section is a fixed physical length, its importance changes by band.

On the lower bands it is a smaller electrical fraction of a wavelength and mainly modifies the current distribution of the whole antenna. As frequency rises, it becomes a more substantial radiator and has a greater effect on pattern and polarisation.

### 80 m

On 80 m, the 4.7 m vertical section is electrically short. Its radiation is likely to be modest compared with the horizontal arms, although it can still alter feedpoint current division, pattern and loss.

The 4:1 UnUn may face demanding low-frequency conditions on 80 m, particularly if the feedpoint impedance is high or reactive. It is therefore reasonable to treat 80 m as a likely transformer-stress case, but not to declare it the worst case without measurement.

### 40 m

On 40 m, the vertical section becomes a more meaningful part of the antenna. It is still well short of a quarter wavelength, but its contribution is no longer incidental. This is likely to be a useful middle ground where the antenna retains strong horizontal-wire behaviour while developing a clearer vertical component.

The lower 1:1 current balun becomes increasingly important because its impedance helps define the length of the radiating shield. Its boundary is strong rather than perfect: finite choke impedance and capacitance can allow some current to continue below it, making choke design and feedline routing part of the installation.

### 20 m

On 20 m, 4.7 m is close enough to a quarter wavelength for the vertical section to become a major influence, although the connected horizontal arms, top loading and choke impedance prevent it from behaving exactly like an isolated quarter-wave vertical.

This is probably where the NKO shows its strongest mixed horizontal and vertical behaviour. It may also become more installation-sensitive because small changes in electrical length and choke behaviour matter more as the vertical section approaches resonance.

The lower 1:1 current balun may experience significant RF voltage on this band even when measured current near its lower end is modest. The band on which the vertical section radiates most strongly is therefore not necessarily the band that produces the greatest heating, voltage stress or transformer stress. The 4:1 UnUn and lower 1:1 current balun need to be assessed separately.

---

## 2. Feedline participation and hybrid behaviour

In the NKO, the outside of the feedline shield above the lower 1:1 current balun is not an accident. It is an intended conductor in the radiating system.

That means the antenna includes:

- the mainly horizontal behaviour produced by the unequal wire arms
- a defined vertical current region on the outside of the coax shield
- the interaction between all three conductors

This is the basis for describing the NKO as a **hybrid antenna**.

### Why that matters

The word “hybrid” is useful, but it should not imply that the NKO delivers the complete performance of a stand-alone OCF and a stand-alone vertical at the same time. The arms and shield are electromagnetically connected and form one current system. Their fields combine into one direction-dependent and polarisation-dependent pattern.

A strongly horizontal or strongly vertical antenna can be excellent when the path suits it and disappointing when it does not. The NKO’s broader mixture of horizontal and vertical behaviour may make it less vulnerable to some changes in arriving direction and polarisation.

The NKO has sometimes been described as a **“single-port diversity antenna.”** That is not a strict engineering definition because there are no independent receiver branches and no active selection or combining. It remains a useful informal description of the design aim: one antenna presenting the receiver with a broader mixture of the signal components present on a real HF path.

That is not a claim of magical gain. It is a claim that the NKO may interact with the path differently from a conventional horizontal wire antenna.

---

## 3. Why does it seem to improve audio?

This is the most controversial part of the NKO story, so it is important to state it carefully.

The reported effect is audio that sounds sharper, clearer, less muffled and easier to understand.

The NKO was not designed as an “audio antenna,” and these reports were unexpected. They have nevertheless been repeated by several operators and have appeared in direct audio comparisons. The observation deserves investigation, but it should not be turned into a claim that the antenna itself equalises the speech spectrum.

Across the few kilohertz occupied by an SSB signal, the antenna’s own pattern changes by a negligible amount. The more credible explanation is what happens in the ionospheric channel:

- a real HF signal often arrives as several copies with different delay, direction, polarisation and phase
- those copies can produce selective fading across the speech passband
- every antenna gives those arriving copies a different relative weighting
- the NKO’s mixed pattern may, on some paths, give a more favourable balance between the main and delayed copies

If a troublesome delayed copy is reduced relative to the main copy, the notches across the recovered speech can become shallower and the voice easier to understand. If the delayed copy is strengthened, the NKO can instead be worse. The proposed advantage is therefore path-dependent and statistical, not guaranteed at every moment.

So the improvement, where it exists, is best thought of as:

> **more usable signal rather than simply more signal**

That matches the reports received so far: punchier, easier copy, hearing more stations clearly, and less of the “through a door” effect.

Reports of punchier transmitted audio do not require the antenna to change the transmitter’s audio response. By reciprocity, a different transmitting pattern and polarisation mixture can excite the available ionospheric paths differently, changing the signal mixture that eventually arrives at the distant receiver.

---

## 4. Signal strength and phase relationships

Some reported signal-strength differences are large enough that pattern change is likely part of the explanation.

Possible contributors include:

- useful current on the vertical section
- changed magnitude and phase relationships among the three conductors
- a stronger response at the particular elevation and bearing of the path
- a better match to the polarisation that arrives or is launched
- lower loss than some comparison arrangements
- different interaction with ground and nearby objects

This is one reason a single NEC peak-gain figure does not settle the matter. A model may show only a modest change in maximum gain while showing a much larger difference at the exact bearing, elevation and polarisation of a particular path. The useful comparison is the complete vector pattern, not only the highest number in the model.

Reported differences of one or two S-points are useful field evidence, but they are not automatically a calibrated dB measurement. Receiver S-meters, AGC action, fading and the reference antenna’s own pattern nulls can all magnify or compress the apparent difference. The strongest cases remain important, but they should be tested simultaneously and accumulated statistically.

---

## 5. Frequency-selective fading and intelligibility

Voice communication over radio is not just about total RF strength. It is also about what happens across the recovered audio passband.

**Frequency-selective fading** occurs when copies of the same signal arrive with different delay and phase. They do not add evenly at every frequency. Some parts of the passband reinforce while others cancel, producing moving peaks and notches across the recovered speech.

A differential delay of only one millisecond produces features spaced roughly one kilohertz apart, easily placing several peaks and notches inside a normal SSB speech channel.

In practice, an HF signal can remain quite strong overall yet sound hollow, rough or difficult to understand. When a notch falls in the upper speech region, consonants and fricatives can be damaged even though the voice is still plainly present. That is why two antennas with similar average signal readings can sound quite different.

The NKO observations make the most sense in that context. The antenna does not repair audio after the ionosphere has damaged it. Instead, its pattern and polarisation response change the relative strength of the arriving paths before they are combined at the receiver input.

A plausible working explanation is that this sometimes produces shallower or shorter-lived spectral notches, improving practical intelligibility even when average signal strength is not dramatically different.

---

## 6. The working position

The best current explanation for the NKO’s observed behaviour is that it changes three important things at once.

1. A conventional OCF is mainly a two-arm horizontal wire antenna. The NKO retains those arms but deliberately includes a defined vertical shield section above the lower 1:1 current balun. The result is one coupled three-conductor antenna with a different current distribution from a normal OCF, dipole or EFHW.

2. That current distribution produces a different directional and polarisation response. The NKO can respond through both horizontal and vertical field components, but these are not independent signal channels and they do not automatically add beneficially. Their phase and magnitude determine the result for each direction and path.

3. The ionosphere presents the antenna with several changing signal components rather than one fixed ray. The NKO may weight those components differently from the reference antenna. On favourable paths this can increase signal strength, reduce the severity of selective fading, or preserve more speech detail.

The strongest present insight is:

> **The NKO’s possible advantage is not simply “horizontal gain plus vertical gain.” It is the particular balance of direction, polarisation and phase produced by the whole connected antenna when it interacts with a real HF path.**

The field reports of stronger signals and improved audio can plausibly arise from:

- better coupling to the useful path or mode
- a more useful launch or receive angle
- a better match to the polarisation present at that moment
- shallower selective-fading notches
- lower effective loss in the complete installation
- a useful contribution from the vertical radiator
- the reference antenna having a less favourable pattern or null on that path

Because the NKO is a passive linear antenna, its underlying pattern, efficiency and polarisation behaviour are reciprocal. Practical receive and transmit reports can still look different because local noise, the distant station’s antenna and changing propagation are not reciprocal parts of the antenna itself.

That is the present working position. It is not a miracle claim and it is not final proof. It is a coherent explanation that fits both the physical structure and the observations well enough to justify serious further testing.

---

## Caveats

A number of things are still open:

- direct measurement of current magnitude and phase on all three radiating conductors
- 4:1 UnUn loss, temperature and stress under the actual complex load on each band
- common-mode impedance, current, RF voltage and temperature at the lower 1:1 current balun
- how much current continues below the lower 1:1 current balun in real installations
- how installation height, soil, feedline routing and nearby objects affect the result
- whether local noise received by the vertical section sometimes offsets the signal benefit
- which path lengths, arrival angles and propagation conditions show the strongest effect
- simultaneous dual-receiver recordings for audio and selective-fading comparison
- long-term WSPR or beacon testing for signal level, fade depth and outage statistics
- comparison against a well-choked horizontal dipole as well as practical references such as an EFHW inverted-L

The common EFHW inverted-L reference is itself not purely horizontal. Its vertical section, slope, radials and possible feedline current can all contribute. Comparisons therefore establish the behaviour of two complete real antennas; they do not by themselves isolate one vertical component.

So the correct status of this document is:

> **working explanation, not final proof**

---

## Selected references

### Antenna behaviour, polarisation and baluns

- Radio Society of Great Britain, *RSGB Radio Communication Handbook*  
  https://rsgb.org/main/publications/books/radio-communication-handbook/

- ARRL, *The ARRL Antenna Book*  
  https://www.arrl.org/arrl-antenna-book

- Roy W. Lewallen, W7EL, **“Baluns: What They Do and How They Do It”**  
  Useful experimental discussion of current balance, feedline current and current versus voltage baluns.  
  https://www.arrl.org/files/file/History/History%20of%20QST%20Volume%201%20-%20Technology/AntComp1-Lewallen%281%29.pdf

- NIST Technical Note 1311, **“Extrapolation Range Measurements for Determining Antenna Gain and Polarization”**  
  Describes antenna coupling and polarisation using complex vector components rather than scalar gain alone.  
  https://nvlpubs.nist.gov/nistpubs/Legacy/TN/nbstechnicalnote1311.pdf

### HF propagation and selective fading

- ITU-R Recommendation F.1487, **“Testing of HF modems with bandwidths of up to about 12 kHz using ionospheric channel simulators”**  
  Describes HF multipath components, differential delay, Doppler spread and the need for simultaneous real-path comparisons.  
  https://www.itu.int/dms_pubrec/itu-r/rec/f/R-REC-F.1487-0-200005-I%21%21PDF-E.pdf

- ITU-R Report P.266-7, **“Ionospheric propagation and noise characteristics pertinent to terrestrial radiocommunication systems design and service planning”**  
  Covers interference fading, polarisation fading and multipath effects in HF systems.  
  https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-P.266-7-1990-PDF-E.pdf

- ITU-R Recommendation P.533, **“Method for the prediction of the performance of HF circuits”**  
  https://www.itu.int/rec/R-REC-P.533

- Australian Government / Space Weather Services, **“Introduction to HF Radio Propagation”**  
  https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro%20to%20HF%20Radio.pdf

- Davies, K., *Ionospheric Radio*, IEE Electromagnetic Waves Series

### Controlled feeder radiation context

- **“Controlled Feeder Radiation”**, *Radio Communication*, May 1990, B. Sykes, G2HCG  
  https://archive.org/stream/RadCom_Magazine_1990-05/RadCom_Magazine_1990-05_djvu.txt

- **“Controlled Feeder Radiation Revisited”**, *Radio Communication*, July 1991, B. Sykes, G2HCG  
  https://electronicsandbooks.com/edt/manual/Magazine/R/RadCom%20RSGB%20UK/199107.pdf

- **“Controlled Feeder Radiation”**, *Communications Quarterly*, Summer 1992, B. Sykes, G2HCG  
  https://www.worldradiohistory.com/Archive-All-Communications/Communicationns-Quarterly/Communications-Quarterly-1992-02-Summer.pdf

---

## Updated Analysis Notes


ChatGPT was updated in July 2026, so I used it in high thinking mode to re-analyse this document and update it with improved analysis.

### 12 July 2026 — OpenAI ChatGPT, GPT-5.6 Thinking

This update retained the original structure, practical tone and working conclusion while re-analysing the antenna, transformer and propagation claims in greater depth.

The main changes were:

- described the NKO as one coupled three-conductor antenna rather than a complete OCF and complete vertical simply added together
- clarified what the 4:1 UnUn connection establishes, while avoiding the claim that short-arm and shield currents remain equal or exactly in phase everywhere
- separated possible 4:1 UnUn stress from lower 1:1 current-balun current, voltage and heating stress, and treated both as matters for measurement
- refined the band-by-band behaviour, especially the growing importance and installation sensitivity of the 4.7 m vertical section on 20 m
- replaced the idea of an antenna “audio response” with the more defensible explanation that the NKO may weight delayed ionospheric signal copies differently and thereby alter selective fading
- clarified why NEC vector patterns, calibrated simultaneous comparisons and dual-receiver recordings are more informative than peak gain or isolated S-meter reports
- added reciprocity, local-noise and reference-antenna cautions while preserving the conclusion that the observations justify further testing
