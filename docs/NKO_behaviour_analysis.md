**Author:** VK3TXD (Richard Holmes)  
**Status:** v0.5  
**License:** CC BY 4.0
Attribution: NKO – New Kallista OCF, Richard Holmes (VK3TXD)
Goal: Behaviour and observations about the NKO antenna

# NKO Antenna: Mechanisms, Observations, and Performance Implications

## Summary

The NKO is not just a conventional OCF with a different transformer.

It is a three-conductor antenna system:

- the apex coupling method is different, it uses a 4:1 **UnUn**
- the vertical feedline section above the lower 1:1 balun is part of the antenna system
- the vertical section is top-fed making it act like a top fed vertical antenna
- the vertical section acting as a vertical radiator may be less influenced by earth because of being top fed
- the resulting current distribution, pattern, and on-air behaviour can differ from a conventional OCF or EFHW
- signal reports and comparisons to other antennas indicate signal strenth enhancements, and audio quality improvements

The purpose of this document is to summarise the main working explanation for the behaviour observed so far.

---

## 1. The UnUn

The NKO uses a **4:1 UnUn** at the apex, and that choice is fundamental to the antenna.

A conventional OCF has two unequal arms, so it is not balanced in the ordinary sense. That means a balun is never working under ideal conditions.

The UnUn does two important jobs here. It transforms impedance, and it bonds the coax shield directly to the short arm. That direct bond is what makes the feedline section part of the antenna system.

Because the shield is directly connected to the short arm, it is driven in phase with it. The feedline current is therefore a direct result of the antenna structure, not something that depends on the UnUn somehow forcing it into existence.

In comparison; 
- A conventional 4:1 current balun on an OCF is being asked to feed an antenna whose two arms are unequal from the outset, so it is never operating in a truly comfortable balanced condition.
- A 4:1 voltage balun is possibly a worse choice, because it is still feeding the same unequal antenna but is less tolerant of that kind of asymmetrical load.
- Using a balun, shield current is largely a symptom of imbalance and produces stress on the core. In the NKO, the UnUn makes shield current part of the design, helps current balance, and becomes a useful part of the antenna.
- In the NKO, the 4:1 UnUn is not trying to correct that basic asymmetry.
- Instead, it:
  - transforms impedance
  - bonds the coax shield directly to the short arm
  - makes that shield current part of the antenna system and driven in phase with the short arm
- That direct connection increases the effective current on the short side by adding the shield current to it.
- This tends to improve current balance against the long arm in a way a conventional OCF cannot achieve as directly.

The result is not magic and it does not guarantee the UnUn has low loss on every band, but it does give the NKO a more natural and physically coherent current structure from the start.

It is also easily possible there is less loss, and less stress on the 4:1 core due to the improved balance.

## How the NKO changes by band

Because the vertical section is a fixed physical length, its importance changes by band. On the lower bands it is a smaller electrical fraction of a wavelength and acts more as an added influence on the overall antenna system. As frequency rises, it becomes a more significant part of the radiator and has a greater effect on how the antenna behaves.

### 80 m

On 80 m, the vertical section is electrically short, so its contribution is likely to be modest. It still adds some vertical component and changes the overall current structure, but the antenna is still behaving mainly as a horizontal wire system.

80 m is likely the hardest band on the UnUn and the least rewarding band for the vertical section, while the 1:1 choke is doing important work defining the feedline boundary but may not yet be seeing its worst common-mode stress.

### 40 m

On 40 m, the vertical section becomes a more meaningful part of the antenna. Its vertical contribution is likely to be useful rather than incidental, and this is probably where the NKO starts to show more obvious hybrid horizontal/vertical behaviour.

40 m is likely the most balanced band overall: the UnUn is still under real load, but the vertical section is now contributing usefully, and the 1:1 choke becomes more important because the feedline section is starting to matter more as part of the antenna.

### 20 m

On 20 m, the vertical section is electrically significant and is likely to be one of the main contributors to the antenna’s overall behaviour. This is probably where the NKO shows its strongest added vertical component and its most obvious mixed-polarisation behaviour.

20 m is likely where the vertical section becomes most useful, so the antenna may show its strongest hybrid behaviour here, while the 1:1 choke becomes increasingly critical in defining the radiating section and the UnUn may be under less low-band magnetic stress but still significant voltage and current stress depending on match.

---

## 2. Feedline participation and hybrid behaviour

In the NKO, the feedline above the lower choke is not an accident. It is an intended conductor in the radiating system.

That means the antenna combines:

- the horizontal wire behaviour of the OCF arms
- the vertical behaviour of the defined coax section (which is driven at the top like a top fed vertical antenna)

This is the basis for describing the NKO as a **hybrid antenna**.

### Why that matters

A strongly single-polarisation antenna can be excellent when the arriving field suits it and disappointing when it does not. The NKO may, on some paths, be less vulnerable because it is not relying on one orientation alone.

In other words it combines the performance of both the horizontal OCF, and the performance of a top fed vertical antenna.

The NKO has been described as a "Single Port Diversity Antenna" - which is not strictly correct but is indicative of how we consider it.

That is not a claim of magical gain. It is a claim that the antenna may interact with a real HF path differently.

---

## 3. Why does it seem to improve audio?

This is the most controversial part of the NKO story, so it is important to state it carefully.

The effect is to make the audio sound sharper, more clear, less muffled, more intelligible.

We did not "design" NKO for this, did not expect it, and reports of NKO giving better audio were unexpected. But they were repeated and confirmed by multiple sources. To be honest, it was difficult to believe and is not commonly mentioned on the internet and it seemed to contradict our expectations of how antennas and radios work. But it is regularly observed to different degrees.

The NKO is **not** being presented as an audio equaliser in the sky.

The better working explanation is:

- real HF paths often suffer from **selective fading**
- selective fading can damage intelligibility without making the signal vanish completely
- NKO being different to an OCF or EFHW, combines both horizontal and vertical components of a signal which may result in better audio

So the improvement where it exists may be better thought of as:

> **more usable and better signal rather than simply more signal**

That matches the kind of reports received so far: punchier, easier copy, hearing more stations better, and less of the “through a door” effect.

---

## 4. Signal strength and phase relationships

Some reported signal-strength improvements are large enough that pattern change is likely part of the explanation.

Possible contributors include:

- stronger or better-positioned current on the vertical section
- changed phase relationships between the three conductors
- lower loss than some comparison arrangements
- different ground interaction
- different launch-angle weighting

This is one of the reasons simple NEC gain comparisons do not settle the matter by themselves. Indeed, NEC can show a comparatively small pattern change yet signal reports indicated 1 to 2 S point improvements regularly compared to a reference antenna.

---

## 5. Frequency-selective fading and intelligibility

Voice communication over radio is not just about total RF strength. It is also about what happens across the recovered audio passband.

**Frequency-selective fading** happens when the same signal arrives by more than one path, or in more than one component, with slightly different delay and phase. When those copies combine at the receiver, they do not add up evenly across the passband. Some parts reinforce. Some parts cancel. The result is a series of peaks and notches across the recovered speech spectrum.

In practice, that means an HF signal can still be quite strong overall yet sound rough, hollow, or harder to understand. The lost parts are often in the upper speech region where consonants and fine speech detail live. That is why two antennas with broadly similar signal reports can still sound very different on air.

The NKO observations make the most sense when viewed in that context. The antenna combines horizontal and vertical components in one structure, and those components need not be affected in exactly the same way by a changing HF path.

A plausible working explanation is that this changes how severely some of the worst spectral notches appear at the receiver, improving practical intelligibility even when average signal strength is not dramatically different.

---

## 6. The working position

The best current explanation for the NKO’s improved performance is that it changes three important things at once.

1. A conventional OCF is a two-arm horizontal antenna. The NKO keeps those two horizontal arms, but also adds a top-fed vertical radiator driven in phase with the short arm. That makes it a different physical system from a normal OCF, dipole or EFHW, because it is no longer just a horizontal wire antenna.

2. Because of that, the NKO does not behave like a strongly horizontal antenna alone. The horizontal wire arms still favour horizontal polarisation, much like an OCF, but the vertical section adds a vertical component as well. That means the NKO can couple to both the horizontal and vertical parts of a real HF signal in a way a conventional horizontal wire antenna cannot. In practical terms, that gives the antenna access to _more_ signal energy a conventional horizontal wire antenna may miss.

3. It changes the way the antenna interacts with the real HF path. On-air performance is shaped not only by the antenna itself, but by the ionospheric channel it is working through. Multipath, fading, changing angle of arrival and changes in polarisation all matter there. If the NKO interacts with that channel differently, then modelled far-field gain alone will not tell the whole story.

NKO from all signal reports has a "gain advantage" with stronger signals, and also improved audio quality on some signals, some of which are quite surprisingly strong. They can only come from;

- better coupling to the path
- a more useful launch angle for that path
- a better match to the polarisation that actually arrives
- lower effective loss in the overall system
- useful contribution from the added vertical radiator

That is the present working position. It is not a miracle claim, and it is not final proof. It is a practical explanation that fits both the structure of the antenna and the behaviour reported so far, and it is enough to justify serious further testing.

---

## Caveats

A number of things are still open:

- direct current measurement on the vertical section
- exact phase relationships by band
- how installation-sensitive the NKO is
- whether the strongest benefit is receive, transmit, or both
- under what path conditions the effect is strongest

So the correct status of this document is:

> **working explanation, not final proof**

---

## References

- Radio Society of Great Britain, *RSGB Radio Communication Handbook*; https://rsgb.org/main/publications/books/radio-communication-handbook/
- ARRL, *The ARRL Antenna Book*; https://www.arrl.org/arrl-antenna-book
- Davies, K., *Ionospheric Radio*, IEE Electromagnetic Waves Series
- ITU-R P.533, *HF Propagation Prediction Method*; https://www.itu.int/rec/R-REC-P.533
- Rappaport, T., *Wireless Communications: Principles and Practice*
- Proakis, J., *Digital Communications*

- **“Controlled feeder radiation”**, *Radio Communication*, **May 1990** (RSGB).  
  Archive.org OCR text: https://archive.org/stream/RadCom_Magazine_1990-05/RadCom_Magazine_1990-05_djvu.txt  

- **“Controlled Feeder Radiation Revisited”**, *RadCom / Radio Communication*, **July 1991** (RSGB).  
  PDF: https://electronicsandbooks.com/edt/manual/Magazine/R/RadCom%20RSGB%20UK/199107.pdf  

- **“Controlled Feeder Radiation”**, *Communications Quarterly*, **Summer 1992**, B. Sykes, G2HCG.  
  PDF: https://www.worldradiohistory.com/Archive-All-Communications/Communicationns-Quarterly/Communications-Quarterly-1992-02-Summer.pdf
