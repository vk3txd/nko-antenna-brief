# NKO And NEC — A Statement of Position

**Author:** VK3TXD (Richard Holmes)  
**Status:** v0.5  
**License:** CC BY 4.0

---

## 1. Introduction — the short version

NEC is an excellent antenna modeller. It is also only _part_ of and not the complete answer for an antenna like the NKO.

The NKO is interesting because it appears to do things on air that are not fully captured by simple static NEC comparisons alone. That does not make NEC wrong. It means the full communication path includes more than the antenna in isolation.

The basic position of this document is:

> **Use NEC to understand the antenna. Use field testing to understand the antenna in the real HF channel.**

---

## 2. What NEC tells us well

NEC is very good at showing:

- current distribution
- feedpoint impedance
- relationships between conductors
- far-field pattern
- launch angle trends
- the effect of height and geometry changes

For the NKO, that is already valuable. NEC can help show that the feedline section is not electrically irrelevant and that the system should be treated as a three-conductor structure, not just a normal OCF wire.

---

## 3. Where NEC stops

NEC does not model the full time-varying HF communication path. It can't. The ionosphere changes over time, sometimes seconds to minutes and that changes propagation.

It does not model:

- changing ionospheric polarisation
- multipath fading over time
- TIDs - Travelling Ionospheric Disturbances
- changing angle of arrival
- local receive noise behaviour
- the way selective fading damages speech copy

Those are not small details. On HF they are part of the lived reality of using an antenna. One example is QSB which can change signal strength from S2 to S9 on extreme paths, over a few minutes.

So when the question is “what is the exact current on this conductor?” NEC is helpful. 
When the question is “why did one antenna sound easier to copy on a real path tonight?” NEC is only part of the answer.

---

## 4. The real HF path

A real HF path is a channel, not just a line between two antennas.

That channel can introduce:

- multipath
- fading
- polarisation change
- angle-of-arrival change
- time variation on scales from seconds to minutes

We talk about signals being reflected from the ionosphere, they are not. They are refracted, bent gradually before returning to earth and that bending can happen aid different heights. An HF signal may also travel some distance within the ionosphere before exiting to earth - so there is no single place or boundary where signals "bounce off". All of this does a few things;

- the polarisation of the signal can change according to the amount of time a signal is within the ionosphere
- path differences cause multiple copies of the same signal to arrive at a receiving antenna at different times causing multipath interference

In practical terms, two antennas with similar static gain numbers can still behave differently on air because they are not coupling to that channel in exactly the same way. A vertical may behave very differently to a horizontal signal because of polarity rotation.

That is the bigger context in which the NKO has to be judged.

---

## 5. Faraday rotation — important, but not the whole story

Faraday rotation matters on HF. It is one of the ways the ionosphere changes the polarisation of the wave between transmitter and receiver.

It is not the only thing going on.

Real HF fading can also involve:

- multipath interference
- skip fading
- focusing and defocusing
- TIDs
- changing mode mix
- ordinary and extraordinary wave behaviour

The NKO documents therefore treat Faraday rotation as an important part of the picture, not the whole picture.

---

## 6. Why a mixed-polarisation antenna can matter

The NKO combines:

- horizontal wire antenna behaviour
- a vertical feedline section acting as an antenna

That does not make it a classical two-channel diversity system. It does make it different from a strongly single-polarisation reference antenna.

A practical way to state the hypothesis is:

> **On some HF paths, a hybrid antenna with mixed horizontal and vertical behaviour may be less vulnerable to some fades than a strongly single-polarisation antenna.**

That is a conditional and path-dependent claim. It is also a physically reasonable one that helps explain the signal reports from NKO users.

---

## 7. Why NEC may undervalue the NKO on air

A static model naturally scores antennas using static quantities such as gain, bandwidth, pattern, and impedance - and we tend to judge them by these values. It is, arguably, all we really have.

But an antenna is used in the real world and interacts with the ionosphere that is not modelled and therefore the results can be highly skewed by that interaction. If an antenna works better with the ionosphere, it will perform better than one that does not - and modelling will not expose that.

Operators care about:

- signal strength, whether a signal stays above the copy threshold
- readability
- consistency
- fade depth

Antenna A may look better in a static plot and still be less useful on air if it falls apart badly during the fades that matter most.

This is one of the reasons a design like the NKO can be more interesting on air than a first-pass NEC comparison suggests.

---

## 8. There are also non-ionospheric reasons model and reality differ

Not every mismatch between model and field result is “the ionosphere.”

Other reasons include:

- real ground differing from the ground model
- coax routing
- mast coupling
- nearby conductors
- wet foliage
- installation asymmetry
- imperfect chokes
- local noise differences

This is especially relevant for the NKO because some of the feed system is part of the antenna. Small installation details can matter more than they would in a more ordinary system.

---

## 9. The specific NKO position

The evidence so far is consistent with NKO performing better than NEC suggests.

NEC generates a static model in isolation, NKO with its both horizontal and vertical components interacts differently with the ionosphere compared to a simple static model. Signal reports indicate more "gain" than NEC does and also audio changes that are suggestive of very different ionospheric interaction. Some of this gain will be because of angle of radiation, and some will be from other reasons.

The NKO should be judged as:

- a three-conductor antenna structure
- in a real installation
- on a real HF path

The current working view is that the NKO may outperform some conventional reference antennas on air because of a combination of:

- changed current distribution
- changed field structure
- changed pattern
- altered interaction with the full HF channel

That is a more serious and more restrained claim than saying “NEC is useless” or “the antenna has mystery gain.”

---

## 10. What we still do not know

Several questions remain open:

- the exact current magnitude on the vertical section, band by band
- the phase relationship between the conductors under real installations
- how installation-sensitive the best behaviour is
- the degree to which local noise helps or hurts the NKO
- where signal-strength effects end and intelligibility effects begin

Those are not reasons to dismiss the antenna. They are reasons to keep measuring.

---

## 11. What NEC can still tell us about the NKO

NEC remains useful for:

- confirming that the feedline section is electrically active
- comparing variants
- checking launch-angle trends
- understanding the effect of changing vertical section length
- looking at current distribution on the three conductors

H/V magnitude alone does not settle the full propagation question. Relative phase matters too. Even so, NEC is still the right tool for the antenna-side part of the problem.

---

## 12. How the NKO should be evaluated

### A. Fast switching against a reference antenna

Compare against an EFHW, dipole, or ordinary OCF with an A/B switch on the same path.

### B. Long observation periods

Short comparisons can be misleading. The more interesting differences may show up during the fades, not at the strongest moments.

### C. Fade-depth statistics

Minimum useful signal can matter more than average signal.

### D. SNR and intelligibility

Recordings, decode success, and practical readability matter. This is especially true if the claimed improvement is in copy rather than raw signal.

### E. Multiple paths

Try local, medium, and DX paths where possible. Different paths stress antennas differently.

### F. Noise observations

Antenna behaviour is only half the receive story. Local noise pickup matters too.

### G. Model correlation

Use NEC to ask sensible structure questions, then compare those predictions with field observations rather than assuming one replaces the other.

---

## 13. Final position

The NKO is not a rebuke to NEC. It is a reminder that NEC answers the antenna question, while on-air use answers the full communication question.

That is particularly important when the antenna under discussion:

- is structurally unconventional
- includes the feed system in the radiator
- is being judged partly by copy quality, not just static gain

The right conclusion is therefore straightforward:

> **Model the NKO seriously. Test it seriously. Do not assume either one is the whole story by itself.**

---

## 14. Challenges - NKO has forced a change in thinking

At a club meeting an old timer with vastly more experience than me stated very firmly that he did not put much faith in NEC modelling. His experience was that it was poor to wrong compared to observations.

At the time I was dismissive as in my mind NEC produced a very good model as to what I could expect in real life if I compared 2 antennas. NEC would tell me which was the better according to what I was evaluating.

Now I believe him much more. He was right, I was wrong. NKO has done this to me.

Going through the technical information about the ionosphere and how HF signals interact with it, it is clear NEC analysis is only one part of the whole story about how an antenna works. The real world, how an antenna interacts with the ionosphere matters a lot.

We know a vertical behaves differently to a horizontal antenna. We know we get QSB. We know the ionosphere refracts our signals but putting that into the big picture of antenna performance is a different story. Indeed, in this analysis investigation into the way the ionosphere works, what it does to HF signals has been remarkable. A lot more happens than I thought.

The classic example is that signals launched from a vertical antenna are well-received by a horizontal antenna some distance away and vice versa. Yet we know there should be a huge signal strength problem as an antenna is best suited to same polarity signals. Yet in real life it works. Why? Why does a vertical antenna launch a vertically oriented signal that is then well received by a horizontal antenna? The ionosphere is the answer and this is what NEC cannot model.

**Yet more challenge** to my long held beliefs happened when signal reports came in saying, definitely, that NKO improved the quality, intelligibility, of some signals dramatically. This did not sound correct. Yet after months of testing by multiple test stations it is still being reported. NEC does not predict this (how could it) - and again it appears that the ionosphere and the way NKO works with it is the answer.

NKO has challenged my understanding and this research has given me more appreciation of the way radio propagation and antennas work.

---

## References

[1] **NEC-2 User’s Guide, Part III**. Discusses modelling over ground, segmentation, and the need to compare unusual or complex models against measurement where possible.  
https://www.nec2.org/other/nec2prt3.pdf

[2] **ITU-R P.531-16 — Ionospheric propagation data and prediction methods required for the design of satellite networks and systems**. Useful here for Faraday rotation, group delay, and related ionospheric effects; especially the inverse-frequency-squared dependence of Faraday rotation.  
https://www.itu.int/dms_pubrec/itu-r/rec/p/R-REC-P.531-16-202509-I!!PDF-E.pdf

[3] **Australian Government / IPS Radio and Space Services — Introduction to HF Radio Propagation**. A practical HF-oriented reference covering multipath fading, polarisation fading, skip fading, TIDs, and HF noise.  
https://www.sws.bom.gov.au/Category/Educational/Other%20Topics/Radio%20Communication/Intro%20to%20HF%20Radio.pdf

[4] **CCIR Report 252-2 — Worldwide characteristics and performance capabilities of HF communication systems**. Includes discussion of horizontal and vertical gains, relative phase, and coupling to ordinary and extraordinary waves.  
https://www.itu.int/dms_pub/itu-r/opb/rep/r-rep-p.252-2-1970-pdf-e.pdf

[5] **Report ITU-R P.266-7 — Ionospheric propagation and noise characteristics pertinent to terrestrial radiocommunication systems design and service planning**. Includes the long-recognised value of polarisation diversity in reducing fading and distortion on HF paths.  
https://www.itu.int/dms_pub/itu-r/opb/rep/R-REP-P.266-7-1990-PDF-E.pdf

[6] **ITU-R Handbook — The Ionosphere and its Effects on Radiowave Propagation**. Useful background on fading mechanisms including interference fading, polarisation fading, absorption fading, skip fading, and selective fading.  
https://www.itu.int/dms_pub/itu-r/opb/hdb/R-HDB-32-1998-PDF-E.pdf
