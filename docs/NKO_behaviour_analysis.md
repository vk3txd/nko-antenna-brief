# NKO Antenna: Mechanisms, Observations, and Performance Implications

This document examines three non-conventional aspects of the NKO antenna system: (1) the use of an UnUn in an off-centre-fed (OCF) configuration, (2) the role of vertical feedline radiation as an active radiating element, and (3) observed improvements in received and transmitted audio intelligibility potentially linked to frequency-selective fading and multipath effects.

The following sections present observations and plausible mechanisms; where causal relationships are proposed, they are identified as hypotheses consistent with established electromagnetic and propagation theory.

---

## Summary

**UnUn with OCF**  
Traditional OCF antennas typically employ a balun to provide impedance transformation and suppress common-mode currents. The NKO departs from this by using an UnUn, primarily for impedance transformation, while permitting controlled interaction between the feedline and the radiating structure. This alters current distribution and challenges assumptions about strict feedline isolation.
A 1:1 balun further down the feedline establishes a boundary for the feedline to become a controlled radiator.

**Feedline Radiation and Hybrid Polarisation**  
The vertical section of the coax feedline between the 4:1 UnUn and the 1:1 choke balun can support common-mode current and contribute to radiation.
This introduces a vertically polarised component alongside the predominantly horizontal radiation of the OCF arms, forming a hybrid polarisation system that may improve performance under varying propagation conditions.
Of note, this feedline performs like an elevated top-fed radiator with the maximum current at the apex.

**Audio Intelligibility and Frequency Selective Effects**  
Field observations indicate improved speech intelligibility, particularly in fricative consonants.
One plausible explanation is reduced frequency-selective fading through polarisation diversity and multipath interaction, preserving higher-frequency audio components critical for intelligibility.

---

## 1. UnUn Behaviour in an OCF Configuration

The use of an UnUn in the NKO configuration intentionally departs from conventional OCF practice.

In a standard OCF dipole antenna, a balun is used to provide impedance transformation while suppressing common-mode current on the feedline.

> Insert diagram here of balun and OCF arms

Although the arms of an OCF antenna are of unequal length, the structure can still support balanced currents. However, the feedpoint impedance and current distribution are inherently asymmetric, placing practical demands on the balun to both transform impedance and maintain current symmetry. In practice, the effectiveness of this suppression depends on the balun design and its choking impedance.

By contrast, in the NKO system the UnUn primarily performs impedance transformation while permitting common-mode current to develop on the feedline. The feedline shield is directly connected to the short arm as a phase bonded pair, allowing it to participate in the overall current distribution.

> Insert diagram here of UnUn schematic and OCF arms.

This results in a three-conductor system comprising the long arm, with the short arm and the feedline shield connected at the UnUn. The antenna must therefore be considered a coupled 3 wire system rather than a simple two-conductor dipole, with the feedline acting as an additional and deliberate radiating element rather than an accidental and purely passive transmission medium.

**Summary:**  
The UnUn provides impedance transformation while allowing the feedline to participate in the radiating system.
The phase relationships between the long arm, and the phase bonded pair of short arm and coax shield may (arguably) contribute to both efficiency of the antenna system, but also to other claims about its enhanced divertity performance.

---

## 2. Feedline Radiation and Hybrid Polarisation

In conventional antenna systems, feedline radiation is generally treated as an undesirable artefact. In the NKO configuration, it is instead encouraged to be a deliberate and functional component of the antenna system.

The vertical section of the coax feedline between the feedpoint and the common-mode choke can support deliberate significant common-mode current and therefore contribute to radiation. This introduces a vertically polarised component to the overall radiation pattern, complementing the predominantly horizontal polarisation of the OCF arms.

Importantly, the phase relationship of the long arm to the phase bonded pair of short arm and vertical coax suggests the NKO may have advantages compared to other antennas with regard to waveform coherence. Of special note, the effect of this will vary by frequency as a result of different current flows in the 3 arms of the radiating structure. The end-resultant waveform is a vector sum that includes the ampliture as well as the phase relationship of the currents.

The answer to the question of "how much current" is flowing on the coax shield is unknown. We have no doubt it will be frequency dependant meaning it will change band by band. From observation of signal strengths and other effects it is surmised that it is enough to affect the radiation pattern and hence system performance.

The resulting structure behaves as a hybrid antenna system with both horizontal and vertical polarisation components. Under ionospheric propagation conditions, where polarisation can rotate and vary due to propagation effects, this may provide a form of polarisation diversity.

This behaviour aligns with principles described in earlier amateur literature on controlled feedline radiation (CFR), although the NKO represents a more structured and repeatable implementation of these effects.

### Why Does It Always Seem To Improve Audio?

The most common challenge to the NKO's observed audio improvement goes like this: _"If the effect is caused by multipath and propagation effects — which are statistical and random — then it should improve audio half the time and make it worse the other half. Why does it seem to always improve?"_

It is a fair challenge. And the short answer is: _the question contains a hidden assumption that, once removed, resolves the apparent paradox._

The assumption is that both antennas — the NKO and the comparison antenna — are equally affected by propagation conditions, and the NKO is simply getting lucky. It isn't. Here is why.

Two things are happening simultaneously on any HF path.

- The first is multipath. Your signal leaves the transmitter and arrives at your receiver via multiple ionospheric paths, each with a slightly different length and therefore a slightly different travel time. These delayed copies combine at the receiver and interfere with each other — constructively at some frequencies, destructively at others. The result is a comb-filter pattern across the audio band, with some frequencies reinforced and others cancelled. This pattern shifts constantly as the ionosphere moves. The frequencies that get cancelled are not random — delay spreads typical of medium to long HF paths consistently place spectral nulls in the 1–4 kHz region. That is precisely where fricative consonants live — the s, f, sh, th sounds that make speech intelligible rather than merely audible. This is why you can hear someone but not understand them. The vowels survive. The consonants don't.
The second is polarisation fading. The ionosphere does not simply reflect or refract your signal — it continuously rotates its polarisation via Faraday rotation, and splits it into ordinary and extraordinary wave components that travel slightly different paths. A signal that left the transmitter horizontally polarised does not arrive horizontally polarised. Its polarisation state is constantly and unpredictably changing.

- A purely horizontal antenna — an EFHW, a standard dipole, a conventional OCF — can only respond to the horizontal component of the arriving wave. When polarisation rotation has shifted the arriving signal away from horizontal, the horizontal antenna fades. Not because the signal got weaker. Because the antenna can no longer see it properly.
Think of polarised sunglasses. Rotate them 90 degrees and the world goes dark — not because the light changed, but because the lens can only receive one orientation. A horizontal antenna in a polarisation fade is exactly that. The signal is there. The antenna is partially blind to it.

**Here is the key point.** These two effects — multipath spectral nulls and polarisation fading — are happening at the same time, and both disproportionately damage the consonant region of the audio band. The horizontal antenna has no defence against either. It receives whatever the propagation channel delivers, degraded by both mechanisms simultaneously.

The NKO has a vertical component — its coaxial feedline section, driven in-phase by the UnUn, radiates vertically as well as horizontally. Both components arrive at the same feedpoint and are combined passively. The receiver sees the sum of both.

This matters for two reasons.

- First, when polarisation fading has reduced the horizontal component, the vertical component is not in the same fade — polarisation fading is by definition polarisation-dependent. The vertical component catches what the horizontal misses.
- Second, the multipath comb-filter pattern is not identical for horizontal and vertical polarisation components — the path geometries differ slightly. 

When the two components combine at the feedpoint, the deepest nulls of one are partially filled by the other. The result is shallower, broader spectral variation rather than deep narrow nulls in the consonant region.

Broadly speaking, it all boils down to NKO being like a diversity antenna system; both horizontal and vertical, and combining them in one.

Here is a technical treatment on Faraday rotation and multi-path effects and how NKO operates. <br>
[Audio Enhancement and A diversity antenna, propagation mechanisms and NKO ](docs/NKO_Propagation_Diversity.md)


**Summary:**  
The NKO deliberately utilises feedline radiation to create a hybrid polarisation antenna system. The extent of this, the relative strengths of the vertical and horizontal components, are unknown at this time.

We consider this to be a plausible hypothesis, that the radiating vertical coax section and the horizonetal OCF arms form a radiating system as described. Our observations of signal strengths and other factors to be discussed lead us to believe that there is an interaction. However;
- we do not have measurement of the NKO arms and coax shield currents
- we do not have comparative measurement of the current in a conventional 'standard' OCF that uses a current balun
- we do not have measurements of relative field strengths
- we do know that NKO does in general have a better signal strength leading us to believe that the use of an UnUn and having the vertical coax radiate, as being the only difference in the antenna, are indeed contributing significantly (but not by how much)

---

## 2a. Signal Strength and Phase Relationships

Field observations have reported variations in received signal strength (improvements) when comparing the NKO to conventional OCF implementations. These differences are consistent with changes in current distribution and radiation geometry resulting from the inclusion of the feedline as an active radiating element, rather than a purely passive transmission line.

In the NKO configuration, the long arm, short arm, and feedline shield form a multi-conductor three element radiating system. Each conductor has a different electrical length and supports a different current distribution, leading to phase differences between their radiated fields. The resulting far-field radiation is therefore the vector sum of multiple contributions with differing amplitudes and phases.

We surmise these phase relationships are not fixed but may vary with frequency, antenna geometry, and operating conditions. Consequently, the NKO may exhibit changes in radiation pattern, elevation angle distribution, and polarisation characteristics when compared to conventional OCF antennas.

In this sense, the NKO behaves more like a loosely coupled three element system than a single wire radiator. While not a controlled array, the interaction between its elements can produce constructive and destructive field combinations that vary with frequency and environment. To date the signal reports indicate constructive field combinations.

Under ionospheric propagation conditions—where multiple refracted paths, time delays, and polarisation states are present—these differences in radiated field structure may interact with the propagation channel. This provides a plausible mechanism for observed variations in both received signal strength and audio intelligibility.

Also by a process of elimination, it is most likely that the vertical coax radiation is responsible. The NKO changes the matching device to an UnUn. How that could change signal strength to the degree observed is unlikely. That leaves the only other change bring the use of the coax as the most likely cause.

**Summary:**  
The NKO forms a multi-conductor radiating system with variable phase relationships, leading to changes in radiation characteristics that can interact with real-world propagation conditions.

---

## 3. Audio Intelligibility and Frequency Selective Fading

This is a 'work in progress' and we are raising it here as a consideration and discussion point. It is an observed characteristic that has been independantly reported.

Field observations from multiple independent stations have reported improved speech intelligibility, particularly in fricative consonants, when using the NKO antenna compared to conventional wire antennas. These observations challenge the common assumption that antennas influence only signal strength and not recovered audio quality.

The effect was first noticed on 20m DX between VK3 and Japan, USA and the UK. Signals on an EFHW were Q0 but of acceptable strength, while on the NKO they were 2 S points stronger but the intelligibility changed to be Q4 to Q5. A similar but less strong response was observed across VK3 on 40m on an approx 360klm path, raising intelligibility from Q2 to Q4. On 80m, DSP analysed audio analysis showed approx 3dB change (lift) on audio frequencies associated with speech fricatives on a 180klm path.

Searches of the internet revealed the effect is not commonly discussed or documented. We conjecture that for NKO it was so quickly observed within a few days of testing because the test stations were using a coax switch and comparing an NKO to their own pre-existing antennas. They were listening for differences, flicking between antennas quickly which is not normally done.

How this can happen has been the target of much research and conjecture.

HF propagation via the ionosphere occurs through refraction within a graded medium, where electron density varies continuously with height rather than forming a discrete reflecting boundary. Signals just do not bounce from a hard medium, rather, they bend gradually over a vertical distance. As a result, transmitted waves are progressively bent back toward Earth, with the exact trajectory determined by frequency, angle of incidence, and the vertical electron density profile.

Under typical conditions, multiple refractive paths can exist simultaneously—arising from different effective refraction heights within the E and F regions, as well as single- and multi-hop geometries—each with a distinct path length and therefore a distinct time of arrival delay. These delayed components arrive concurrently at the receiver and combine as a vector sum, producing constructive and destructive interference that varies with frequency, time, and polarisation.

Because the delay spreads are commonly on the order of microseconds to milliseconds, they give rise to frequency-selective fading across the audio passband, where some frequency components are reinforced while others are attenuated. In this context, the antenna system forms part of the effective propagation channel, not merely the radiator.

Time delay differences between multipath components determine the frequency spacing of constructive and destructive interference. As a rule of thumb, a delay Δt produces a comb-filter effect with nulls spaced at approximately 1/Δt in frequency.

Typical relationships are:

- Δt ≈ 0.1 ms (100 µs) → path difference ≈ 30 km → null spacing ≈ 10 kHz (minimal audible effect)
- Δt ≈ 0.5 ms → path difference ≈ 150 km → null spacing ≈ 2 kHz (affects upper speech components)
- Δt ≈ 1 ms → path difference ≈ 300 km → null spacing ≈ 1 kHz (noticeable speech coloration)
- Δt ≈ 2–3 ms → path difference ≈ 600–900 km → null spacing ≈ 300–500 Hz (significant intelligibility impact)
- Δt > 5 ms → path difference > 1500 km → null spacing < 200 Hz (slow spectral variation, “hollow” audio)

These delay and path length differences are consistent with HF ionospheric propagation, where variations in refraction height, hop count, and ground interaction points can readily produce path differences of tens to thousands of kilometres.

They also reinforce the observations showing lesser change in shorter paths, and greater differences on DX with strongest on 20m as the band of greatest difference (longest paths hence longer delays). Also it is easy to suggest this may be strongly condition sensitive with the way the ionosphere refracts signals playing a key role.

From observations on 80m and 40m where the path lengths are shortest and hence the possibility of significant time delay differences are the smallest, we suggest that fricatives, concentrated toward the upper end of the SSB passband, are most sensitive to moderate delay spreads (on the order of 0.5–2 ms). This is where the comb-filter null spacing falls within the 1–3 kHz region. Under these conditions, relatively small changes in the relative amplitudes and polarisations of multipath components—such as those introduced by a hybrid-polarisation antenna—can produce disproportionately large changes in perceived intelligibility. Put simply, these high pitch parts of the SSB audio band are the most easily affected.

The current theory is that a hybrid polarisation antenna may reduce selective attenuation of higher-frequency audio components by providing multiple propagation paths with differing polarisation states, thereby improving perceived intelligibility. Why it selects better intelligibility as opposed to worse remains unknown.

It is suggested that improvements may be more noticeable than degradation.

The NKO configuration does not inherently increase signal information content, but may reduce the severity of frequency-selective fading. In HF propagation, multipath effects often produce deep spectral nulls within the audio passband, particularly in the 2–4 kHz region critical for speech intelligibility. These nulls can significantly degrade received audio.

By introducing a hybrid polarisation and multi-element radiation structure, the NKO effectively provides partial diversity. The resulting signal at the receiver can be viewed as the combination of multiple components with differing phase and polarisation characteristics. Because these components are not fully correlated, deep fades in one component are often partially filled by others.

This process tends to reduce the depth of spectral nulls rather than introduce new severe attenuation. As a result, the received audio spectrum may exhibit reduced deep fading and more uniform frequency response. From a perceptual standpoint, shallow spectral variation is less detrimental to intelligibility than deep, narrow nulls, leading to a subjective improvement in clarity.

It should be noted that this effect is statistical rather than deterministic. Under certain conditions, destructive combination may occur, and no universal improvement can be assumed. However, in typical HF multipath environments, a reduction in deep frequency-selective fading provides a plausible explanation for the observed tendency toward improved intelligibility.

Resolving this theory will require more testing and the use of DSP analysis of recorded speech.

**Summary:**  
Multipath propagation and frequency-selective fading provide a plausible mechanism linking antenna characteristics to observed differences in audio intelligibility.

We consider this to be an unresolved area of study and disclose it as such;
- we have a limited sample size and number of observations
- all evidence suggest _something_ is happenening, we are choosing a possible and most likely hypothesis 

---

## Caveats
Much of the above is AI generated and has been verified as much as is practical. Using AI has its own inherent risks. It does however remain and should be considered speculative.

- No direct current or pattern measurements have been done
- Observations are anecdotal/field-based from a small number of stations, but they have been repeated
- Proposed mechanisms are consistent with theory but require empirical confirmation (e.g., current probes, field strength comparisons, more audio analysis)

We invite peer review and others to replicate and report.

---

## References

- Radio Society of Great Britain, *RSGB Radio Communication Handbook*, various editions; https://rsgb.org/main/publications/books/radio-communication-handbook/
- ARRL, *The ARRL Antenna Book*; https://www.arrl.org/arrl-antenna-book
- Davies, K., *Ionospheric Radio*, IEE Electromagnetic Waves Series
- ITU-R P.533, *HF Propagation Prediction Method*; https://www.itu.int/rec/R-REC-P.533
- Rappaport, T., *Wireless Communications: Principles and Practice*
- Proakis, J., *Digital Communications*

- **“Controlled feeder radiation”**, *Radio Communication*, **May 1990** (RSGB).  
  Archive.org OCR text: https://archive.org/stream/RadCom_Magazine_1990-05/RadCom_Magazine_1990-05_djvu.txt  
  (“Controlled feeder radiation” or “G2HCG”.)

- **“Controlled Feeder Radiation Revisited”**, *RadCom / Radio Communication*, **July 1991** (RSGB).  
  PDF: https://electronicsandbooks.com/edt/manual/Magazine/R/RadCom%20RSGB%20UK/199107.pdf  
  (“CONTROLLED FEEDER RADIATION REVISITED”.)

A reprint/alternate publication also appears as:
- **“Controlled Feeder Radiation”**, *Communications Quarterly*, **Summer 1992**, B. Sykes, G2HCG.  
  PDF: https://www.worldradiohistory.com/Archive-All-Communications/Communicationns-Quarterly/Communications-Quarterly-1992-02-Summer.pdf