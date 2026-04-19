<!-- NKO-DOC-HEADER -->
<!--
License: CC BY 4.0 (documentation/design) — see LICENSE
Attribution: NKO – New Kallista OCF, Richard Holmes (VK3TXD)
Goal: This document is part of the NKO repository. It aims to be practical, reproducible, and evidence-led.
-->

# NKO Antenna: Propagation, Diversity, and Intelligibility

**Status:** Public (alpha)  
**Author:** VK3TXD (Richard Holmes)  
**License:** CC BY 4.0  
**Part of the NKO repository** — see [README](../README.md)

---

## A Note On This Document

This document addresses a specific and initially puzzling observation about the NKO antenna: that it consistently produces improvements in received audio intelligibility that do not always correlate with signal strength as shown on an S-meter or signal report.

This is not a claim about magic. It is an attempt to identify the physics behind a real and repeatable observation, and to place it in a framework that experienced HF operators and technically minded readers can evaluate for themselves.

_The mechanisms described here — multipath propagation and polarisation fading as causes, frequency-selective fading as their principal effect on audio, and polarisation diversity as the NKO's partial answer to both._

The actual cause and effect chain is:

Causes:
- Multipath propagation;  multiple signal copies arriving via different ionospheric paths with different time delays
- Faraday rotation and ionospheric birefringence; continuously rotating and splitting the signal's polarisation state

Effects:
- Frequency-selective fading; result of multipath time delay differences producing comb-filter interference across the audio band
- Polarisation fading;  result of Faraday rotation and birefringence making a single-polarisation antenna periodically blind to the arriving signal



All are well established in communications engineering literature and are referenced later.

What is less well established, particularly in accessible amateur radio literature, is how they interact, and how antenna design choices affect them.

---

## 1. The Amateur Radio Antenna And State of the Art

Amateur radio operators have been building and using HF antennas for over a century. In that time, the collective wisdom has converged on a well-understood set of parameters by which any antenna is evaluated and compared: **gain, radiation pattern, bandwidth, and impedance**. These four parameters describe what an antenna does, how well it does it, and how well it connects to the radio. They are the language of antenna comparison, the basis of NEC modelling, and the framework behind every antenna review in every amateur radio publication.

Within this framework, the choice of antenna comes down to a practical binary: **horizontal or vertical**. Horizontal antennas — dipoles, OCFs, EFHWs, loops — are understood to favour higher-angle radiation and horizontal polarisation. Vertical antennas favour low-angle radiation and vertical polarisation. Operators choose based on space, budget, target bands, and operating preference. Both work. Both are well understood.

What is rarely questioned is whether the **polarisation characteristic of the antenna affects received signal quality beyond what the four parameters capture**. Gain, pattern, bandwidth and impedance say nothing about how an antenna behaves when the arriving signal's polarisation has been scrambled by the ionosphere, or when multipath delay has carved spectral nulls into the audio passband.

This document examines that gap — and the NKO antenna exists precisely because of it. The NKO challenges the assumption that these four parameters are sufficient to describe antenna performance, and questions the orthodoxy that horizontal and vertical are the only choices that matter. It suggests that a hybrid antenna, deliberately combining both polarisations at a single feedpoint, can produce a qualitative improvement in received signal that no S-meter will show and no NEC model will predict.

---

## 2. What Multipath Propagation Is

HF signals travelling via the ionosphere do not arrive at a receiver via a single clean path. The ionosphere is not a hard mirror — it is a graded medium where electron density varies continuously with height, bending signals gradually back toward Earth across a vertical distance. Under typical conditions, multiple refracted paths exist simultaneously, arising from different effective refraction heights within the E and F regions, as well as single-hop and multi-hop geometries. Each path has a distinct length, and therefore a distinct travel time.

These delayed copies of the same signal arrive at the receiver simultaneously and combine as a vector sum. Where they add constructively, the signal is reinforced. Where they add destructively, the signal is cancelled. Because the delay differences between paths are typically on the order of microseconds to milliseconds, the constructive and destructive interference does not affect the whole signal equally — it affects some frequencies more than others. This is **frequency-selective fading**.

The relationship between path delay and audio effect is straightforward:

| Path Delay | Path Difference | Null Spacing in Audio |
|---|---|---|
| ~0.1 ms | ~30 km | ~10 kHz — minimal audible effect |
| ~0.5 ms | ~150 km | ~2 kHz — upper speech components affected |
| ~1 ms | ~300 km | ~1 kHz — noticeable speech coloration |
| ~2–3 ms | ~600–900 km | ~300–500 Hz — significant intelligibility impact |
| >5 ms | >1500 km | <200 Hz — slow spectral variation, hollow audio |

The result is a comb-filter effect on the received audio — certain frequency ranges are attenuated or cancelled while others are reinforced. Crucially, this comb pattern is not fixed. It shifts with time as the ionosphere moves and changes, producing the characteristic fading and warbling sound familiar to any HF operator.

Multipath effects are strongest on longer paths, which is consistent with observations that NKO performance differences are most pronounced on 20m DX paths, and less dramatic on shorter 80m and 40m contacts.

---

## 3. What Polarisation Fading Is

Polarisation fading is a separate mechanism from multipath, though the two occur simultaneously and interact. It is less widely understood in amateur radio circles, and its effects are often attributed to other causes.

When a linearly polarised HF signal enters the ionosphere, two things happen. First, the ionosphere is birefringent — it splits the signal into two characteristic waves, the ordinary and the extraordinary, which propagate at different speeds and are refracted back to Earth via slightly different paths. Second, the Earth's magnetic field causes **Faraday rotation** — a continuous rotation of the signal's plane of polarisation as it travels through the ionosphere.

The result is that a signal transmitted with horizontal polarisation does not arrive at the receiver with horizontal polarisation. The polarisation state of the arriving wave is continuously and unpredictably changing — rotating, tilting, and shifting between linear, elliptical, and sometimes near-circular polarisation states. This change can be slow or fast, and it is largely independent of signal strength.

This matters enormously for a single-polarisation antenna. A horizontal antenna is maximally sensitive to horizontally polarised signals and relatively insensitive to vertically polarised signals. When Faraday rotation has shifted the arriving signal's polarisation significantly away from horizontal, the horizontal antenna suffers a **polarisation fade** — a loss of received signal that has nothing to do with path loss, absorption, or multipath geometry.

A useful analogy: polarised sunglasses block light that is polarised at 90 degrees to their lens orientation. Rotate the sunglasses 90 degrees and the world goes dark — not because the light got weaker, but because the antenna (the lens) can no longer receive it. A horizontal HF antenna in a polarisation fade is exactly this. The signal is there. The antenna cannot see it.

---

## 4. How Multipath and Polarisation Fading Interact

Multipath and polarisation fading are independent mechanisms, but they compound each other in ways that disproportionately affect speech intelligibility.

Multipath creates spectral nulls — frequency ranges within the audio passband where signal components cancel. Polarisation fading reduces the overall received signal level in a polarisation-dependent way. When both occur simultaneously, as they typically do on HF, the result is a received signal that is both spectrally distorted and variably attenuated.

The speech band runs roughly from 300 Hz to 3 kHz for SSB communications. Vowel sounds carry energy predominantly in the lower part of this range. Consonants — particularly fricatives such as s, f, sh, and th — carry their distinguishing energy in the upper part, from roughly 2 to 4 kHz. These high-frequency consonants are what make speech intelligible rather than merely audible. You can hear someone speaking without being able to understand them — the vowels come through but the consonants are lost.

Multipath delay spreads of 0.5 to 2 ms produce comb-filter nulls with spacing in the 500 Hz to 2 kHz range — directly overlapping the consonant region. A relatively small change in multipath geometry or polarisation state can place a deep spectral null precisely where fricatives live, reducing intelligibility dramatically while leaving signal strength largely unchanged.

This is why the effect shows on your ears before it shows on your S-meter. The S-meter is measuring average received power. Intelligibility is determined by whether specific narrow frequency bands within the speech spectrum are intact.

---

## 5. Why Single-Polarisation Antennas Are Vulnerable to Both

A purely horizontal antenna — an EFHW, a standard dipole, a conventional OCF — samples only one polarisation component of the arriving wave. Under ideal conditions this is not a problem. Under real HF propagation conditions it is a persistent and significant limitation.

When the arriving wave's polarisation has rotated away from horizontal, the horizontal antenna's response falls. This is not a failure of the antenna — it is a fundamental consequence of sampling only one axis of a two-dimensional quantity. The signal has energy in both the horizontal and vertical polarisation components. The horizontal antenna discards the vertical component entirely.

Similarly, when multipath geometry creates spectral nulls in the audio passband, a single-polarisation antenna has no mechanism to mitigate them. The signal it receives is the full result of whatever destructive interference the propagation channel has produced. There is no second channel, no alternative path, no redundancy.

The four standard antenna parameters — gain, pattern, bandwidth, impedance — do not capture either of these vulnerabilities. A high-gain horizontal antenna is more vulnerable to polarisation fading than a lower-gain one, because its higher directivity means it samples an even narrower slice of the polarisation space. NEC modelling will not reveal this. Antenna reviews will not mention it. It is simply outside the framework that amateur radio has traditionally used to evaluate antennas.

---

## 6. What Polarisation Diversity Is and How It Normally Works

Polarisation diversity is a well-established technique in communications engineering for mitigating polarisation fading. The principle is straightforward: if you receive the same signal on two antennas with orthogonal polarisations — one horizontal, one vertical — the fading on each antenna is largely uncorrelated. When the horizontal antenna is in a polarisation fade, the vertical antenna is not, and vice versa. By combining or selecting between the two received signals, the system maintains a more consistent received signal level.

This technique is used extensively in mobile communications infrastructure, where base stations routinely employ cross-polarised antenna pairs at ±45 degrees precisely because the polarisation of signals from mobile handsets is unpredictable and constantly changing. The improvement in reliability is well documented and quantified.

In traditional implementations, polarisation diversity requires two physically separate antennas, two receiver front ends, and a combining or selection circuit. It is a system-level solution, not an antenna-level one. For amateur radio operators this is impractical — most stations have one antenna and one radio.

** A familiar example from amateur radio practice makes this concrete. **

Operators working amateur satellites routinely use a **crossed Yagi** — two Yagi antennas mounted on the same boom at 90 degrees to each other, one horizontally polarised and one vertically polarised, fed with a 90-degree phasing harness to produce circular polarisation.

The reason this is standard practice is exactly the problem described above. A satellite tumbling in orbit presents a continuously and unpredictably changing polarisation to the ground station — but that is only part of the story. The signal also passes through the ionosphere on the way up and on the way down, and Faraday rotation acts on it both times. At VHF the rotation is less severe than at HF, but it is not negligible, particularly at low elevation angles where the signal traverses a longer ionospheric path, and during periods of high solar activity.

The crossed Yagi receives both polarisation components simultaneously — neither is discarded, both contribute to the received signal. Ask any satellite operator why they use one and the answer is immediate: Faraday rotation. The ionosphere rotates the polarisation of the signal on the way up and again on the way down, and a single polarisation Yagi cannot track that rotation. The crossed Yagi is the standard solution, and every operator using one has already accepted — whether they use the term or not — that polarisation diversity is necessary, effective, and worth building into an antenna system.

This is polarisation diversity. It is considered completely normal and unremarkable in the satellite operating community. It is standard equipment.

The ionosphere does exactly the same thing to HF signals — Faraday rotation continuously and unpredictably rotates the polarisation of every signal on every path. The crossed Yagi addresses this at VHF without most operators realising it. The NKO addresses the same problem at HF deliberately and by design. The frequency is different. The physics is the same.

---

## 7. The NKO Approach — Diversity in a Single Antenna

The NKO antenna is a hybrid radiating system. Its horizontal OCF arms provide horizontal polarisation. Its vertical coaxial feedline section — driven in-phase with the short arm by the 4:1 UnUn — provides a vertical polarisation component. Both components are present simultaneously, connected at the same feedpoint, and delivered to the same receiver input.

This means the NKO is receiving both the horizontal and vertical polarisation components of the arriving wave at the same time. It does not switch between them. It does not select the stronger one. It combines them, passively, at the feedpoint. The receiver sees a vector sum of both.

In practical terms: when Faraday rotation has shifted the arriving signal's polarisation away from horizontal, the NKO's vertical component is still responding to it. When the horizontal component is in a polarisation fade, the vertical component is not in the same fade — because polarisation fading is, by definition, polarisation-dependent. The two components fade independently, and their combination at the feedpoint produces a more consistent composite signal than either alone.

This is a form of polarisation diversity achieved within a single antenna structure. It is not a deliberate design goal borrowed from communications engineering — it is an emergent consequence of the NKO's hybrid architecture. But the mechanism is the same, and the benefit is the same: reduced susceptibility to polarisation fading, and by extension, more consistent received audio quality.

The degree of vertical component in the NKO is frequency-dependent and not yet precisely quantified. The phase relationship between horizontal and vertical components varies with frequency and installation geometry. These are open questions. But the existence of a meaningful vertical component is supported by the field observations, and the mechanism by which it produces intelligibility improvements is physically coherent.

---

## 8. Why Improvement Is Asymmetric — Answering the Sceptic

A reasonable challenge to the observed improvement is this: *"If the effect is due to multipath and polarisation fading — which are statistical processes — then the NKO should improve audio half the time and degrade it the other half. Why does it seem to only ever improve?"*

This is a good question, and it deserves a direct answer.

The question assumes the comparison is symmetric — that the NKO and the EFHW are equally affected by propagation conditions, and the NKO sometimes gets lucky. This is not what is happening.

The EFHW is a single-polarisation antenna. It is already degraded whenever polarisation fading has shifted the arriving signal away from horizontal. It has no mechanism to recover that signal. In those moments, it is receiving a weakened, spectrally distorted version of what was transmitted.

The NKO is not in the same degraded state at those moments. Its vertical component is still responding. The composite signal at its feedpoint is less affected by the polarisation fade than the EFHW's signal.

So the comparison is not between two antennas with equal baseline performance, one of which gets randomly lucky. It is between an antenna that is vulnerable to a common ionospheric condition, and one that is partially resilient to that same condition. The improvement is not random — it is systematic. It occurs specifically in the conditions where the EFHW is most disadvantaged.

To put it simply: **a horizontal-only antenna is wearing polarised sunglasses. When the ionosphere rotates the light, it goes partially blind. The NKO has both lenses — horizontal and vertical — and catches what the horizontal alone would miss. You are not choosing the best signal. You are not throwing half of it away. You are getting both.**

The improvement appears asymmetric because the baseline — the comparison antenna — is already compromised in the conditions where the NKO shows its advantage. The NKO is not occasionally better. It is consistently less vulnerable.

---

## 9. What This Means for Intelligibility Specifically

Signal strength and intelligibility are not the same thing, and on HF they frequently diverge.

A signal can be strong enough to move the S-meter and still be difficult to copy, because multipath has placed a spectral null across the consonant region of the audio band. Conversely, a weaker signal with an intact spectral response can be perfectly readable. Experienced HF operators know this intuitively — "armchair copy" is not always the strongest signal in the log.

The NKO's benefit to intelligibility operates through two related mechanisms:

**First**, reduced polarisation fading depth means the overall received signal is more consistent. Fewer deep fades means fewer moments where the signal drops below the threshold of readability.

**Second**, and more subtly, the hybrid polarisation structure means that the spectral nulls produced by multipath are different in the two polarisation components. Multipath geometry is polarisation-dependent — the path delay differences, and therefore the comb-filter null positions, are not identical for horizontal and vertical polarisation components arriving from the same transmitter. When these two slightly different comb-filter patterns are combined at the feedpoint, the deepest nulls of one are partially filled by the other. The result is a received audio spectrum with shallower, broader spectral variation rather than deep, narrow nulls.

Shallow spectral variation is far less damaging to intelligibility than deep nulls. The ear and brain are remarkably good at compensating for gradual spectral tilt. They are much less able to reconstruct speech when specific frequency bands are entirely missing. A 6 dB broad roll-off is far more intelligible than a 20 dB narrow null at 3 kHz — even though the total signal power loss may be similar.

This explains the specific character of the improvement observers report. Not "louder" — "clearer." Not "stronger" — "more punchy." Not more signal, but more of the signal that carries meaning. Fricatives restored. Consonants recovered. The difference between hearing someone speak and understanding what they said.

---

## 10. What We Don't Yet Know

This document presents a physically coherent hypothesis, not a proven and measured result. The following remain open questions:

- **The magnitude of the vertical component** in the NKO feedline is frequency-dependent and has not been directly measured. Current probes on the coax shield would quantify this.
- **The phase relationship** between horizontal and vertical components varies with frequency and installation geometry. Whether this relationship is consistently beneficial, or varies in ways that sometimes reduce the diversity benefit, is unknown.
- **The relative contribution** of polarisation diversity versus multipath null-filling to the observed intelligibility improvement has not been separated.
- **Conditions of strongest effect** — path length, ionospheric state, time of day, band — have been noted qualitatively from field reports but not systematically mapped.
- **The sample size** of field observations remains small. Results are consistent across those observations, but a larger and more controlled study is needed.

The honest position is: the mechanism is plausible, the observations are real and consistent, and the explanation offered here is the most physically coherent one available. It requires empirical confirmation through current measurement, field strength comparison, and recorded audio analysis.

---

## 11. How to Test It Yourself

If you want to evaluate the NKO's intelligibility behaviour against a reference antenna, the following methodology will produce the most reliable results:

**Equipment needed:**
- NKO antenna and a reference antenna (EFHW, dipole, or standard OCF)
- A coaxial A/B antenna switch
- Ideally, a recording device (phone, PC audio, SDR) to capture audio for later comparison

**Method:**
- Connect both antennas to the A/B switch with matched feedline lengths where practical
- Select a signal that is present but not armchair copy — a signal where you are working to read it
- Switch between antennas and listen for differences in clarity, not just strength
- Pay specific attention to consonants — can you hear the difference between S and F sounds? Does one antenna make the speaker easier to understand even at similar apparent strength?
- Record audio from both antennas on the same signal if possible — spectral analysis of recordings can reveal comb-filter null patterns directly

**What to note:**
- Band and approximate path length to the station
- Time of day and ionospheric conditions if known
- Whether improvement (or otherwise) correlates with signal strength change or is independent of it
- Any difference in the character of fading — depth, speed, spectral character

Reports from testing, including location, ground type, antenna heights, and feedline length, are welcomed and will contribute to the ongoing validation of the NKO design.

---

## 12. A Note On NEC Modelling And Its Limitations For The NKO

NEC modelling is the standard tool for amateur radio antenna analysis, and the NKO repository includes NEC models for the antenna's geometry. These models are useful for evaluating gain, radiation pattern, takeoff angle, and feedpoint impedance — the four standard parameters. They are worth using and worth examining.

However, it is important to understand what NEC cannot tell you about the NKO, and why the far-field plot does not — and cannot — reflect the performance observations described in this document.

NEC computes antenna behaviour assuming a fixed, coherent, deterministic signal. It models a single plane wave arriving from a given direction with a fixed polarisation state, and calculates the antenna's response to it. It has no concept of polarisation fading, because it cannot model a signal whose polarisation is continuously rotating due to Faraday rotation in the ionosphere. It has no concept of multipath, because it cannot model two or more delayed copies of the same signal arriving simultaneously with different path lengths, polarisation states, and phase relationships. And critically, it has no concept of diversity gain — the benefit that comes from combining two partially uncorrelated signal components at a single feedpoint. That benefit does not exist in NEC's mathematical framework, so NEC cannot predict it.

The consequence is straightforward: when you compare an NKO far-field plot to an EFHW far-field plot in NEC, you are comparing two static snapshots of gain versus angle. That comparison is valid for what it measures. It is simply the wrong test for what the NKO is claiming. The NKO's advantage lies not in its static radiation pattern but in how it samples a constantly changing, polarisation-rotating, multipath-affected propagation channel. NEC sees a photograph. The real ionosphere is a river.
This does not mean NEC modelling of the NKO is without value — it confirms the antenna is well-behaved, gives useful guidance on feedline length optimisation, and establishes a baseline. But if a sceptic asks for the NEC model as the primary evidence for or against the intelligibility improvement, they are applying the right tool to the wrong question. The evidence for the diversity benefit must come from the real world — from A/B comparisons, recorded audio, and field reports. That is where this project is headed.

---

## 13. Terms and Concepts

Who knew that NKO would trigger such a research article that explored such intracacies of ionospheric propagation? In this research, many terms have been encountered that the casual user of Amateur Radio may not be aware of.

Of particular note is that the terms have been researched from stated references and every effort has been made to ensure their accuracy.

The references section is _worthwhile reading_ particularly some of the amateur level discussions about polarization diversity.

---

### Multipath Propagation

When an HF signal travels via the ionosphere it does not arrive at the receiver via a single clean path. The ionosphere is not a hard mirror — it is a graded medium where electron density varies continuously with height, bending signals gradually back toward Earth across a vertical distance. Under typical conditions, multiple refracted paths exist simultaneously. These arise from different effective refraction heights within the E and F layers, from single-hop and multi-hop geometries, and from ground reflections between hops.

Each path has a distinct length and therefore a distinct travel time. The signal copies arriving via these different paths combine at the receiver as a vector sum — adding constructively at some frequencies and destructively at others.

The result is **frequency-selective fading** — not the whole signal fading uniformly up and down, but specific frequency ranges within the audio band being reinforced or cancelled depending on the path delay differences. This produces the characteristic warbling, hollow, or distorted sound familiar to any HF operator on a long path.

Multipath effects are strongest on longer paths, which is consistent with field observations that NKO performance differences are most pronounced on 20m DX contacts and less dramatic on shorter 80m and 40m paths.

---

### Frequency-Selective Fading

Frequency-selective fading is the **result** of multipath propagation. It is not a separate cause — it is what multipath does to the received signal.

When two or more delayed copies of the same signal combine at the receiver, they interfere constructively at some frequencies and destructively at others. The spacing of the constructive and destructive interference in the frequency domain — the comb-filter pattern — depends on the time delay difference between paths. Larger delay differences produce more closely spaced nulls.

For HF propagation the relationship between path delay and audio effect is:

| Path Delay | Path Difference | Null Spacing in Audio |
|---|---|---|
| ~0.1 ms | ~30 km | ~10 kHz — minimal audible effect |
| ~0.5 ms | ~150 km | ~2 kHz — upper speech components affected |
| ~1 ms | ~300 km | ~1 kHz — noticeable speech coloration |
| ~2–3 ms | ~600–900 km | ~300–500 Hz — significant intelligibility impact |
| >5 ms | >1500 km | <200 Hz — slow spectral variation, hollow audio |

The critical region for speech intelligibility is 1–4 kHz. Fricative consonants — s, f, sh, th — carry their distinguishing energy in this region. These are the sounds that make speech intelligible rather than merely audible. When multipath places a spectral null in this region, you can hear someone speaking but not understand them. The vowels survive. The consonants do not.

This is why frequency-selective fading is the link between antenna polarisation behaviour and perceived audio quality. A reduction in the depth of spectral nulls in the 1–4 kHz region produces a disproportionate improvement in intelligibility — not because the signal is stronger, but because the parts of the signal that carry meaning are no longer being cancelled.

---

### Faraday Rotation

Faraday rotation is the continuous rotation of a radio wave's plane of polarisation as it travels through the ionosphere. It is named after Michael Faraday, who observed the same effect in glass placed in a magnetic field in 1845. The ionosphere, threaded by the Earth's magnetic field, produces the same effect on radio waves.

The mechanism: the Earth's magnetic field causes free electrons in the ionosphere to respond differently to left-hand and right-hand circularly polarised components of a radio wave. A linearly polarised wave can be understood as the sum of equal left-hand and right-hand circular components. In the ionosphere those two components propagate at slightly different speeds, accumulating a phase difference between them. When they recombine, the resulting linear polarisation is rotated relative to the original.

The rotation is not fixed. It varies continuously with:

- **Frequency** — the rotation angle is inversely proportional to the square of the frequency. A signal on 40m suffers considerably more rotation than the same signal on 20m, and 80m more again. Lower bands are disproportionately affected.
- **Electron density** — higher electron density produces more rotation. Daytime, high solar activity, and equatorial regions all increase the effect.
- **Path length** — a longer path through the ionosphere accumulates more rotation.
- **Earth's magnetic field** — the effect is strongest when the propagation direction is parallel to the magnetic field lines, and varies with geographic location.

The practical consequence for HF operators is that a signal transmitted with horizontal polarisation does not arrive with horizontal polarisation. The polarisation state of the arriving wave is continuously and unpredictably shifting — rotating, tilting, sometimes passing through vertical, sometimes becoming elliptically or near-circularly polarised. This is **polarisation fading**.

---

### Ionospheric Birefringence

Birefringence means the splitting of a wave into two components that travel at different speeds through a medium. The word comes from optics — certain crystals such as calcite split a beam of light into two beams that travel at different speeds through the crystal and exit with different polarisations. The same physical phenomenon occurs in the ionosphere with radio waves, because the ionosphere is not an isotropic medium — the Earth's magnetic field makes it behave differently in different directions.

When a radio wave enters the ionosphere, the magnetic field forces it to split into two distinct propagation modes: the **ordinary wave** and the **extraordinary wave**. These travel at different speeds, follow slightly different paths, and return to Earth with different polarisation states. On recombination at the receiver they produce a resultant wave whose polarisation differs from what was transmitted — and which varies as the ionosphere changes.

Ionospheric birefringence works alongside Faraday rotation. Together they make polarisation fading an unavoidable feature of HF propagation over any path of significant length.

---

### Ordinary and Extraordinary Waves

When ionospheric birefringence splits a radio wave into two components, these are the names for those two components. The terms come from 19th century optics, where the same splitting was observed in certain crystals. One component behaved as expected — following the standard rules of refraction. The other did not — hence ordinary and extraordinary.

In the ionosphere:

The **ordinary wave** (O-mode) is circularly polarised in the left-hand sense. It behaves predictably, following the standard rules of ionospheric refraction largely as if the Earth's magnetic field were not present. It has a refractive index determined primarily by the electron density of the ionosphere.

The **extraordinary wave** (X-mode) is circularly polarised in the right-hand sense. It behaves differently — it travels at a different speed, refracts at a different angle, and is reflected back to Earth from a different height than the ordinary wave. Its refractive index is determined by both electron density and the Earth's magnetic field, making its behaviour more complex and more variable.

Both waves started as your single transmitted signal. They travel through the ionosphere separately, accumulating different path lengths and different travel times. When they exit the ionosphere and recombine, they produce a linearly polarised wave — but with a polarisation plane that is rotated relative to what was transmitted. This rotation is the physical mechanism of Faraday rotation and is the fundamental reason why polarisation fading on HF is unavoidable with a single-polarisation antenna.

An important practical note: in some ionospheric conditions the ordinary and extraordinary waves can arrive at the receiver at sufficiently different times to be heard as distinct signal components. This is occasionally visible on SDR waterfall displays as a signal that appears to split into two closely spaced traces — a direct observation of birefringence in action.

---

### Polarisation Fading

Polarisation fading is the **result** of Faraday rotation and ionospheric birefringence. It is what those mechanisms do to the received signal at a single-polarisation antenna.

A purely horizontal antenna — a dipole, an EFHW, a conventional OCF — is maximally sensitive to horizontally polarised signals. Its response to a vertically polarised signal is minimal. Its response to a signal at an intermediate polarisation angle is proportional to the cosine of the angle between the signal's polarisation and the antenna's polarisation axis.

When Faraday rotation and birefringence continuously shift the arriving signal's polarisation away from horizontal, the horizontal antenna's response falls in proportion. At 45 degrees of rotation the antenna is receiving approximately 3 dB less signal than it would from a horizontally polarised wave of the same strength. At 90 degrees of rotation it is almost blind to the signal.

This is not a failure of the antenna. It is a fundamental consequence of sampling only one axis of a two-dimensional quantity. The signal has energy in both the horizontal and vertical polarisation components. A single-polarisation antenna discards whichever component does not match its orientation.

A useful analogy: polarised sunglasses block light that is polarised at 90 degrees to their lens orientation. Rotate the sunglasses and the world goes dark — not because the light got weaker, but because the lens can no longer receive it. A horizontal HF antenna in a polarisation fade is exactly this. The signal is there. The antenna cannot see it.

Polarisation fading is distinct from multipath fading in its mechanism, but the two occur simultaneously on any real HF path and compound each other. The combination produces fading that is both spectrally selective and polarisation-dependent — a more complex and more damaging degradation than either mechanism alone.

---

### Polarisation Diversity

Polarisation diversity is the technique of receiving both horizontal and vertical polarisation components of the arriving wave simultaneously, so that when one is in a polarisation fade the other is not.

The principle is well established in communications engineering. Polarisation fading affects horizontal and vertical components independently — when Faraday rotation has rotated the arriving signal toward vertical, the horizontal antenna fades but the vertical antenna does not. The fades on the two polarisation components are largely uncorrelated. By combining or selecting between the two received signals, the system maintains a more consistent received signal level regardless of the instantaneous polarisation state of the arriving wave.

This technique is used extensively in mobile communications infrastructure. Base stations routinely employ cross-polarised antenna pairs at ±45 degrees because the polarisation of signals from mobile handsets is unpredictable and constantly changing. The improvement in reliability is well documented, quantified, and commercially deployed at scale.

In traditional implementations, polarisation diversity requires two physically separate antennas, two receiver front ends, and a combining or selection circuit. For most amateur radio operators this is impractical.

The NKO achieves a form of polarisation diversity within a single antenna structure. Its horizontal OCF arms respond to horizontal polarisation. Its vertical coaxial feedline section responds to vertical polarisation. Both are connected at the same feedpoint and delivered to the same receiver input. The receiver sees the combination of both polarisation components simultaneously — not selected between, not switched, but summed. The result is a received signal that is less vulnerable to polarisation fading than a single-polarisation antenna, because when one component fades the other does not fade to the same degree.

---

## 14. References and Further Reading
### Ionospheric Propagation — General

- Davies, K., *Ionospheric Radio*, IEE Electromagnetic Waves Series
  The standard academic reference on ionospheric radio propagation. Covers all propagation modes, Faraday rotation, ordinary and extraordinary waves, and the Appleton-Hartree equation in depth.

- ITU-R P.533, *HF Propagation Prediction Method*
  The international standard method for HF propagation prediction. Authoritative.
  https://www.itu.int/rec/R-REC-P.533

- Jenn, D.C., *Ionospheric Wave Propagation*, Naval Postgraduate School
  Freely available PDF. Covers the Appleton-Hartree equation, ordinary and extraordinary wave modes, Faraday rotation, and phase velocity differences in rigorous but accessible engineering terms. Recommended for technically oriented readers.
  https://faculty.nps.edu/jenn/EC3630/Ionosphere(v1.6.5).pdf

- ZL1BPU, *An Introduction to HF Propagation and the Ionosphere*
  Amateur radio level. Includes real ionosonde spectrogram data showing ordinary and extraordinary rays visibly separating — a direct observation of ionospheric birefringence. The right starting point for most amateur radio readers.
  https://www.qsl.net/zl1bpu/IONO/iono101.htm

- AFRL, *Wave-Optics Modeling of High-Frequency (HF) Propagation*, AFRL-RY-WP-TR-2023-0013
  US Air Force Research Laboratory technical report. Covers diffraction, interference, and wave-optics effects in HF propagation that ray-tracing methods miss.

---

### Faraday Rotation and Polarisation Fading

- Scientific Reports, *Estimation of Faraday Rotation and Polarization Loss Based on 3D Electron Density for Space Surveillance Radar*, 2025
  Peer reviewed. Covers recombination of ordinary and extraordinary waves on ionospheric exit, rotation angle variation with frequency, electron density, and elevation angle. Confirms the inverse square relationship between rotation angle and frequency.
  https://www.nature.com/articles/s41598-025-26733-3

- Cannon, P. et al., *A Simple Polarisation Fading Model for HF Propagation in the Ionosphere*, IET Conference Publication, IEEE Xplore
  Develops an analytical polarisation fading model using ray tracing. Covers Faraday rotation effects on HF signal polarisation.
  https://ieeexplore.ieee.org/document/1350435/

- Zaalov, N. et al., *Fading in the HF Ionospheric Channel and the Role of Irregularities*, ScienceDirect, 2013
  Directly confirms the splitting of HF signals into ordinary and extraordinary waves with different paths and speeds, and the resulting change in polarisation at the receiver. Also covers multipath and amplitude fading mechanisms.
  https://www.sciencedirect.com/science/article/abs/pii/S0273117713002081

---

### Polarisation Diversity

- LZ1AQ, *Horizontally Polarized Small Active Receiving Antennas*
  Amateur radio level. Directly addresses polarisation fading at HF, the uncorrelated fading of horizontal and vertical antennas on the same mast, and the improvement available from combining them. Strongly recommended — directly relevant to the NKO diversity argument and written for an amateur radio audience.
  https://www.lz1aq.signacor.com/docs/hpsra/horizontally-polarized-small-active-receiving-antennas7.htm

- Microwave Journal, *Polarization Diversity Antennas for Compact Base Stations*
  Engineering level. Covers diversity gain theory, branch correlation, combining methods, and the conditions under which maximum diversity benefit is achieved. The clearest treatment of why diversity gain is not symmetric.
  https://www.microwavejournal.com/articles/2844-polarization-diversity-antennas-for-compact-base-stations

- ScienceDirect Topics, *Polarization Diversity*
  Concise overview of polarisation diversity theory, branch correlation, and combining methods. Good entry point.
  https://www.sciencedirect.com/topics/engineering/polarization-diversity

---

### Amateur Radio Reference

- Radio Society of Great Britain, *RSGB Radio Communication Handbook*
  Standard amateur radio reference. Covers HF propagation, antenna theory, and practical antenna construction.
  https://rsgb.org/main/publications/books/radio-communication-handbook/

- ARRL, *The ARRL Antenna Book*
  Standard amateur radio antenna reference. Covers antenna theory, design, and construction across all HF bands.
  https://www.arrl.org/arrl-antenna-book

---

### Controlled Feeder Radiation — Historical

These articles predate the NKO and document the earliest known amateur radio work on deliberate feedline radiation as part of an antenna system. They are the historical foundation on which the NKO concept builds.

- Sykes, B. (G2HCG), *Controlled Feeder Radiation*, Radio Communication (RSGB), May 1990

- Sykes, B. (G2HCG), *Controlled Feeder Radiation Revisited*, Radio Communication (RSGB), July 1991
  https://electronicsandbooks.com/edt/manual/Magazine/R/RadCom%20RSGB%20UK/199107.pdf

- Sykes, B. (G2HCG), *Controlled Feeder Radiation*, Communications Quarterly, Summer 1992
  Reprint of the above in a US publication.
  https://www.worldradiohistory.com/Archive-All-Communications/Communicationns-Quarterly/Communications-Quarterly-1992-02-Summer.pdf

---

### NKO Repository Documents

- [README.md](../README.md) — NKO overview and design brief
- [NKO_behaviour_analysis.md](NKO_behaviour_analysis.md) — mechanisms, observations, and performance implications
- [NKO_Component_Notes.md](NKO_Component_Notes.md) — balun, UnUn, OCF, NCW, and NKO component detail
- [NKO_soil_interaction.md](NKO_soil_interaction.md) — ground effects and soil interaction
- [NKO_Misconceptions.md](NKO_Misconceptions.md) — common misconceptions addressed
- [NKO_Propagation_Diversity_And_Intelligibility.md](NKO_Propagation_Diversity_And_Intelligibility.md) — propagation, diversity, and intelligibility
- [NKO_Propagation_Terms_And_Concepts.md](NKO_Propagation_Terms_And_Concepts.md) — glossary of propagation terms used in NKO documentation

---

## Author
Richard Holmes VK3TXD

**Revisions**
- April 2026 — Initial release
