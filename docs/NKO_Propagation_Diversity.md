# NKO Antenna: Propagation, Multipath, and Intelligibility

## Overview

This document goes deeper into the propagation side of why the NKO may behave differently on air compared to what we expect from modelling and experience. The NEC position paper also deals with this.

I have included this in an attempt to better understand propagation and how NKO works as an antenna. 

The question behind it is simple:

> **Why might the NKO sometimes sound easier to copy than a familiar reference antenna, even when simple modelling does not suggest a dramatic gain advantage?**

The answer proposed here is not “magic” and not “it adds treble.” The working explanation is that the NKO’s hybrid structure may interact differently with a real HF channel — particularly one affected by multipath, polarisation change, and selective fading.

Independent observations from users of NKO are that:
- It has a signal strength advantage
- Some contacts sound a lot better, with much more intelligible speech

This is a **working explanation**, not a final proof.

---

## 1. The HF channel is part of the problem

An NEC antenna model describes the antenna. A real contact includes the ionosphere and path as well.

On HF, that path is not stable and simple. It can involve:

- multiple ionospheric modes
- multiple path lengths
- ordinary and extraordinary waves
- changing polarisation
- changing angle of arrival
- focusing and defocusing
- TIDs - Travelling Ionospheric Disturbances
- selective fading across the passband

That is why antennas that look similar in simple static terms do not always sound similar on air.

---

## 2. Multipath in plain language

Multipath means the receiver is hearing more than one version of the same transmission at once, usually arriving with slight time delays between them.

Multipath happens when the same HF signal arrives by two or more ionospheric paths with different lengths, creating the tiny delays that can range from a few tens or hundreds of microseconds to several milliseconds and longer.

Those versions arrive with:

- different delay
- different phase
- different amplitude
- sometimes different polarisation, because different ionospheric modes and paths can evolve differently

When they combine, some frequencies reinforce and some cancel. On SSB that can make speech sound rough, hollow, nasal, or simply harder to understand.

That is why a signal can still be “there” yet not be easy to copy.

---

## 3. Polarisation fading in plain language

If a wave were to stay purely horizontal all the way from transmitter to receiver, a horizontal antenna would always be happiest (best signal report) and a vertical antenna would be strongly mismatched.

Real HF does not behave like that. The ionosphere changes the wave as it travels. It can rotate the wave from one polarisation to another and all angles between.

That is why horizontal-to-vertical and vertical-to-horizontal contacts are everyday events on HF. Launched polarisation is not preserved. We accept that without thinking about the why or how of it.

It is also why NKO can sometimes have a signal advantage over a strongly single-polarisation antenna.

NKO has both horizontal and vertical sensitivity, so it is not limited to just one preferred polarisation. The receiver sees one combined result from the whole antenna structure. This is not the same as two independent diversity channels, and the contributions do not always add in a favourable way: their phase can produce reinforcement, partial cancellation, or simply a different balance. The useful point is that NKO responds differently from a mainly horizontal reference when the arriving polarisation is changing.

Because of the ionosphere rotating a wave, a strongly single-polarisation antenna can work well one minute and lose signal strength the next, even though neither operator has touched a thing. This changing mismatch can be one cause of QSB (fading), because the received signal fades as the arriving polarisation moves away from what the receiving antenna favours.

Travelling Ionospheric Disturbances, or TIDs, can add to this by changing the phase, amplitude, polarisation and angle of arrival of the wave as they pass through the refracting region of the ionosphere. In practice, that means QSB can wax and wane over anything from fractions of a second or a few seconds to much slower changes lasting many seconds or minutes, depending on what the ionosphere is doing.

**Fading is happening for a few reasons.** A single polarity antenna may lose sensitivity because the incoming wave has rotated out of its plane of best performance. Also multiple copies of the wave may arrive simultaneously with small time delays causing cancellation or reinforcement that changes over time.

*References*
- Australian Bureau of Meteorology, *Introduction to HF Radio Propagation*.
- ITU-R Report P.266, *Ionospheric Propagation and Noise Characteristics Relevant to HF Broadcasting*.

---

## 4. Selective fading is the practical audio problem

For speech work, the most relevant fading is often not complete disappearance. It is **frequency-selective fading**.

This damages some parts of the speech band more than others.

The practical result is familiar:

- the signal meter may not look catastrophic, or even change much at all
- the voice may still be present and sound quite strong
- but consonants, fricatives, and speech detail are harder to recover - the higher pitch sounds like 'sh' and 't' and 'ch' are reduced or missing.

This is exactly why “it sounds stronger” and “it sounds clearer” are not the same report.

Frequency Selective fading can sound like listening to a conversation in another room through a door so that it appears muffled and hard to understand.

This is not something that after 20 years of using HF radio we were aware of until we used NKO and compared it to an EFHW antenna. We found NKO for some contacts sounded significantly better, sharper, clearer. Contacts receiving signals from NKO reported it sounded more 'punchy'.

---

## 5. Why a conventional single-polarisation antenna can struggle

A conventional horizontal wire antenna can be excellent. So can a conventional vertical. The point here is not that they are bad antennas.

The point is that they are limited in how they couple to a changing polarisation path, because each favours its own polarisation. When the path changes arriving polarisation away from what they are most sensitive to, they lose effectiveness.

If the arriving field and the selective-fading pattern happen to suit them, they can sound superb. If not, they can become frustratingly hard to copy without the signal disappearing entirely.

That is the real setting in which NKO comparisons should be understood.

---

## 6. What classical polarisation diversity is

In communications engineering, polarisation diversity normally means:

- two branches (two antennas)
- two orthogonal polarisations (vertical and horizontal)
- some degree of branch independence (they are separated)
- some form of selection or combining

That is the benchmark.

The NKO is **not** that.

The NKO has a single feedpoint and a single passive sum from both a horizontal antenna (OCF arms) and a vertical antenna (vertical coax sheath).

So this document does **not** claim classical two-branch diversity gain in the strict communications-engineering sense.

---

## 7. The NKO approach — a mixed-polarisation antenna

The NKO is a hybrid radiating system. Its horizontal OCF arms contribute primarily horizontal behaviour, while its radiating feedline section contributes vertical behaviour. Both are present at the same time and arrive at the receiver through the same feedpoint.

That means the NKO does not behave like a conventional single-polarisation wire antenna. It does not switch between horizontal and vertical behaviour, and it does not actively choose the stronger one. Instead, the receiver sees the passive result produced by the whole connected antenna structure.

That passive result should not be pictured as two clean signals being added with a guaranteed improvement. Depending on the arriving direction, polarisation and phase, the contributions can reinforce, partly cancel, or change the balance between the several copies of the signal arriving through the ionosphere.

On a real HF path, where polarisation, delay, and angle of arrival all change with time, that broader response can still be useful. A strongly single-polarisation antenna can be very good when the path suits it and poor when it does not. The NKO’s mixed horizontal and vertical behaviour may make it less vulnerable to some of those changes.

Put simply, the NKO gives the receiver one combined signal formed from a wider mixture of directions and polarisations than a strongly single-polarisation wire. That creates an opportunity for better copy, not an automatic win.

That is the practical claim.

---

## 8. Why this may help intelligibility

There are two linked reasons this may matter.

### First

If the arriving field does not stay neatly aligned with one antenna orientation, a hybrid antenna may spend less time being badly mismatched.

The antenna system responds through both its horizontal and vertical parts, producing one combined signal for the receiver.

### Second

Multipath means that several copies of the transmission may arrive with different delays, directions and polarisations. Every antenna gives those copies a different emphasis. The NKO may sometimes favour the main copy more than a delayed copy, making the speech-band notches shallower and the voice easier to understand. On another path it could do the opposite, so the effect is not guaranteed.

The important idea is not that the NKO somehow repairs damaged audio. It changes the mixture of arriving signal copies before they reach the receiver. On favourable paths, that different mixture may preserve more of the speech detail even when average signal strength is not dramatically different.

That is a modest claim, but it is enough to explain why an antenna might sound easier to copy without needing to invoke mystery gain.

---

## 9. What this does **not** mean

It does **not** mean:

- the NKO is a guaranteed improvement on every path
- the NKO is classical diversity
- the NKO is a treble booster
- every mixed-polarisation antenna must improve intelligibility
- phase and correlation do not matter

They do matter.

The simple presence of horizontal and vertical components is not by itself proof of benefit. The balance and phase relationship between them are also important, and those vary with band and installation.

---

## 10. Why 20 m often comes up

Several of the early reports have drawn attention to the 20 m band.

There are three likely reasons:

- The vertical coax is close to a quarter wavelength on 20 m, making it a stronger contributor there.
- The vertical component from the coax can lower the launch angle more on 20 m, favouring DX and potentially improving signal strength.
- On 20 m, the paths are often the longest, which may mean greater polarisation change as well as larger multipath delays.

This makes it plausible that NKO shows its strongest benefit on 20 m, with a lesser effect on 40 m and less again on 80 m. A defined vertical coax section that is a more useful fraction of a wavelength can contribute more strongly on the higher HF bands than it does on 80 m. If that changes both launch-angle behaviour and the way the antenna couples to the arriving signal, the difference may be easier to notice there.

This is one reason the NKO should be thought of as a band-dependent antenna, not an antenna with the same behaviour on every band.

---

## 11. Why the effect may not be symmetric

A common question is: if NKO helps in difficult conditions, why does it not always sound dramatically better?

Because the advantage may live mostly in the **bad moments**, not the best ones.

A reference antenna may sound excellent when the path happens to suit it and NKO might not sound much different.

The NKO may earn its keep by sounding **less bad** during the fades that make the reference antenna struggle. That can produce a real practical advantage without a giant average signal increase.

This is very different from “always sounds louder.”

---

## 12. Why does NKO so often produce better audio? Why not sometimes worse?

This is the sharpest question anyone can ask about the NKO.

> If multipath delays, polarisation and arrival angles all vary, why do the reports seem mainly positive? Should not a passive antenna sometimes make the combination worse as well as better?

Yes. In principle, it can.

The NKO has one feedpoint and no active diversity combiner. Its horizontal and vertical contributions can reinforce, partly cancel, or give greater weight to a delayed signal copy. It can therefore be worse on a particular signal, at a particular moment. Local noise received by the vertical section is another possible disadvantage.

The more useful explanation for the mainly positive reports is that the noticeable advantage may occur mostly during the otherwise **bad moments**.

When both antennas give easy copy, the difference may be too small to attract attention. When propagation is so poor that neither gives useful copy, there may be no comparison to report. The striking cases occur near the intelligibility threshold: the reference becomes hollow, muffled or difficult, while the NKO preserves enough consonants and speech detail to remain readable.

This does not require the NKO to win every instant. It only requires it to produce fewer, shallower, or shorter bad periods often enough to be noticed. A modest change in how the antenna weights the main and delayed signal copies can sound much larger than it looks on an S-meter when it moves speech from just below to just above the threshold of understanding.

There is also an important caution about the common EFHW inverted-L reference. It is not a perfect horizontal-only laboratory antenna. Its vertical wire section, sloping section, radials and possible feedline current can all contribute to its response. The field comparison therefore tests the complete behaviour of two real antennas. It does not prove that the NKO alone receives vertical polarisation while the EFHW does not.

### The short answer

The NKO can sometimes be worse. The present field reports suggest that its practical value may be statistical rather than absolute: it may reduce the frequency or severity of the moments that damage intelligibility on some paths.

That is a less dramatic claim than saying the randomness always favours the NKO, but it is more physically defensible and remains consistent with the observations so far.

---

## 13. What still needs measuring

Several things remain open:

- direct current measurement on the vertical section and comparison to OCF arm currents
- the relative phase of the horizontal and vertical contributions
- how strongly the effect depends on installation
- whether local noise sometimes offsets the receive benefit
- which path lengths and conditions show the effect most strongly
- how much of the benefit is receive-side, transmit-side, or both
- simultaneous recordings from two closely matched SDR receive channels, so the same fading event can be compared on both antennas
- long-term WSPR comparisons for signal level, decode rate and fade statistics, while recognising that narrowband WSPR cannot directly show notches across a 3 kHz SSB speech channel

These are not afterthoughts. They are the next useful measurement questions.

---

## 14. Working conclusion

The NKO is best understood as a hybrid antenna with mixed horizontal and vertical behaviour.

Field reports indicate it is worthwhile and it does indeed have advantages.

That alone does not guarantee anything. It does make it plausible that the antenna may interact differently with:

- a changing polarisation state
- a selective-fading path
- a multipath channel carrying speech

That is enough to make the on-air reports coherent without exaggerating them.

The safest statement is:

> **The NKO may, on some HF paths, be less vulnerable than a strongly single-polarisation antenna to the combination of polarisation change and selective fading that damages speech intelligibility.**

That is the working explanation. It is strong enough to be meaningful and restrained enough to remain honest.

---

## Selected references

### HF propagation and ionospheric behaviour

- **Australian Government / IPS Radio and Space Services, _Introduction to HF Radio Propagation_**  
  Practical HF-oriented reference covering multipath fading, polarisation fading, TIDs, noise, and skip behaviour.  
  https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro%20to%20HF%20Radio.pdf

- **ITU-R Handbook, _The Ionosphere and its Effects on Radiowave Propagation_**  
  Background on interference fading, selective fading, polarisation fading, and other HF mechanisms.  
  https://www.itu.int/dms_pub/itu-r/opb/hdb/R-HDB-32-1998-PDF-E.pdf

- **ITU-R Report P.266-7, _Ionospheric propagation and noise characteristics pertinent to terrestrial radiocommunication systems design and service planning_**  
  Includes the recognised value of polarisation diversity in reducing fading and distortion on HF paths.  
  https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-P.266-7-1990-PDF-E.pdf

- **ITU-R P.531**, ionospheric propagation data and prediction methods.  
  Useful for Faraday rotation and related ionospheric effects.  
  https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.531-16-202509-I!!PDF-E.pdf

### Amateur-radio and controlled-feeder-radiation context

- **RSGB Radio Communication Handbook**  
  Standard amateur reference for propagation and antenna work.  
  https://rsgb.org/main/publications/books/radio-communication-handbook/

- **ARRL Antenna Book**  
  Standard antenna reference.  
  https://www.arrl.org/arrl-antenna-book

- **B. Sykes, G2HCG, _Controlled Feeder Radiation_, Radio Communication (RSGB), May 1990**

- **B. Sykes, G2HCG, _Controlled Feeder Radiation Revisited_, Radio Communication (RSGB), July 1991**  
  https://electronicsandbooks.com/edt/manual/Magazine/R/RadCom%20RSGB%20UK/199107.pdf

- **B. Sykes, G2HCG, _Controlled Feeder Radiation_, Communications Quarterly, Summer 1992**  
  https://www.worldradiohistory.com/Archive-All-Communications/Communicationns-Quarterly/Communications-Quarterly-1992-02-Summer.pdf

### Related NKO documents

- [README.md](../README.md)
- [NKO_behaviour_analysis.md](NKO_behaviour_analysis.md)
- [NKO_And_NEC_Position.md](NKO_And_NEC_Position.md)
- [NKO_soil_interaction.md](NKO_soil_interaction.md)
- [NKO_Misconceptions.md](NKO_Misconceptions.md)

---

## Author

Richard Holmes VK3TXD

---

## Updated Analysis Notes

Much of this document is AI generated. I spend a lot of time reviewing, questionning and second guessing AI. I also play off different AIs against each other, checking; Grok, Claude and ChatGPT to arrive at what is presented. It is not just a simple re-package of AI prose.

But time moves on and AI models change and improve, plus the learning available on the internet which AI bases its answers on changes and hopefully improves.

So of course it is sensible to re-process this repository and use the best possble (paid) AI analysis to regularly fact check and update the content.

Here is a list of what has been done as part of that process.

### 12 July 2026 — OpenAI ChatGPT, GPT-5.6 High Thinking

This update retained the document’s structure, practical tone and overall working conclusion while changing as little as possible.

The main changes were:

- clarified that the NKO produces one passive combined response, not two independently selected diversity signals
- replaced the claim that propagation randomness can only favour the NKO with a more defensible statistical explanation centred on fewer or shallower bad moments
- explained in plain language that the antenna may change the relative weighting of the main and delayed signal copies, which can alter selective fading and intelligibility
- noted that a practical EFHW inverted-L is not purely horizontally polarised, so comparisons are between two complete real antenna systems
- added simultaneous dual-receiver audio recording as the strongest direct test, with WSPR retained for longer-term signal and fading statistics

