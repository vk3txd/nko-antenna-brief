# NKO And NEC — A Statement of Position

**Author:** VK3TXD (Richard Holmes)  
**Status:** v0.4  
**License:** CC BY 4.0

---

## 1. Introduction — The Short Version

NEC is an excellent antenna tool. It can model current distribution, feedpoint impedance, radiation pattern, launch angle, and the relationship between conductors in an antenna system. It tells us a great deal about what the antenna itself is doing.

HF communication, however, is never only an antenna problem.

A real HF path also includes ground, local environment, receiver noise, and above all the ionospheric channel. On that path the wave can be refracted, split into multiple modes, arrive from more than one angle, change polarisation, and fade in ways that NEC does not model [2][3][6].

That is simply the nature of HF.

The NKO was not created from a theory of ionospheric diversity. It emerged from a practical feed-system experiment. Once on-air observations began to show differences that were not obvious in simple NEC comparisons, the natural question followed: **what part of the real HF problem is being seen on air that is not present in the static model?**

The position taken in this paper is straightforward:

**NEC models the antenna well, but the full behaviour of an HF communication path depends on more than the antenna alone.**

That view will not surprise many long-time amateurs. Old hands have often remarked that some antennas behave better or worse on air than a simple model might suggest. That does not mean NEC is faulty. It means HF operation includes a real propagation channel whose behaviour can dominate what operators actually experience.

---

## 2. What NEC Tells Us

NEC remains one of the most useful tools available to antenna experimenters.

It is very good at the jobs it was built for:

- calculating current distribution on conductors
- estimating feedpoint impedance
- showing radiation pattern and launch angles
- comparing one physical geometry against another
- helping with matching and multiband behaviour
- showing whether the feedline is likely to be carrying common-mode current if it is included in the model

That is real value. It is why NEC has remained useful for decades [1].

For a conventional antenna in a reasonably clean environment, NEC can often get the experimenter very close to reality. Even with unusual antennas it can still be extremely helpful, provided it is used to answer the questions it is actually capable of answering.

So the starting point here is not criticism of NEC. The starting point is that NEC gives a reliable description of the **antenna side** of the problem.

---

## 3. Where NEC Fits In The Larger HF Picture

NEC models the antenna and its immediate electromagnetic environment. It does **not** model the time-varying HF propagation channel.

That distinction is central.

NEC can tell us:

- how much horizontal and vertical field the antenna may launch
- at what elevation angles that energy leaves
- how current divides between the conductors
- how changing wire lengths, heights, or feed arrangements alters the pattern

A real HF path then adds further effects that sit outside the NEC solution:

- what the ionosphere does to the wave after launch
- whether the received signal is dominated by one mode or several
- how much multipath fading will occur
- how much the signal polarisation rotates on the way
- whether the receiving site has high vertically polarised man-made noise
- whether, over time, one antenna stays above the copy threshold better than another

Those are not small details. On HF they are part of normal operating reality [2][3][6].

There is also a second point that belongs here. Even before ionospheric effects are considered, NEC models and real installations can differ because of **ground accuracy, segmentation, nearby conductors, feedline routing, and common-mode details**. The NEC manual itself is open about this. Finite-conductivity ground approximations have limited accuracy for structures close to ground, and unusual or complex structures benefit from comparison with measurement where possible [1].

So the practical position is this:

**When NEC and field observations differ, the difference may come from the model, the installation, the ionosphere, or a mixture of all three.**

That is not a weakness in NEC. It is the real scope of the problem.

---

## 4. The World HF Actually Lives In

HF radio operates in a moving, imperfect, time-varying channel.

A simple explanation says the signal “bounces” off the ionosphere. That is useful shorthand. The more accurate picture is **refraction through ionised layers** whose properties vary with height, time of day, season, solar activity, latitude, and geomagnetic conditions [2][3].

As the wave enters regions of changing electron density, its path bends. Under suitable conditions it bends enough to return to Earth. Depending on frequency, launch angle, and ionospheric state, more than one propagation mode may exist at once. The receiver may then see more than one version of the signal, arriving with different amplitudes, phases, delays, angles, and polarisation states [3][6].

That behaviour is part of everyday HF operation.

The BOM propagation notes describe several distinct fading mechanisms on HF, including:

- **multipath fading** — different modes or paths arriving together and interfering
- **polarisation fading** — the arriving wave’s polarisation changing relative to the receiving antenna
- **skip fading** — especially near skip-zone boundaries and around sunrise and sunset
- **focusing and defocusing** caused by travelling ionospheric disturbances (TIDs) [3]

The ITU handbook also notes that interference fading can come from multiple reflected skywaves, the ordinary and extraordinary magneto-ionic waves, and scattered components from irregularities [6].

So the received HF signal is often not one stable object. It is the vector sum of several unstable ones.

**Travelling Ionospheric Disturbances (TIDs)** are moving, wave-like ripples in the ionosphere.

In practical amateur-radio terms, they are disturbances passing through the refracting region of an HF skywave path. 

As one moves through that region it can slightly raise, lower, tilt, focus or defocus the part of the ionosphere carrying the signal, which in turn can change the signal’s strength, phase, apparent arrival angle, and sometimes its polarisation.

The result at the receiver can be slow fading, changing skip behaviour, and periods where a path becomes stronger, weaker, or simply less stable even though nothing has changed at either end.

TIDs are thought to arise mainly from wave motion travelling up from below — especially atmospheric gravity waves caused by weather systems and other lower-atmosphere disturbances — and also from auroral and geomagnetic activity following solar events.

---

## 5. Faraday Rotation — Important And Part Of The Picture

Faraday rotation belongs in this discussion because it is both real and operationally important.

When a linearly polarised wave passes through the ionosphere, the magnetised plasma causes the plane of polarisation to rotate. The ITU gives the rotation as being proportional to the integrated electron content and magnetic field along the path, and inversely proportional to the square of frequency [2]. In practical terms: **lower frequencies tend to suffer more rotation than higher frequencies, all else being equal**.

This means that a signal launched as mainly horizontal may arrive at the far end as some other linear polarisation, or as a more complicated elliptical state. If the receiving antenna strongly prefers one polarisation, the received level can vary as the incoming wave rotates [2][3][6].

That is a genuine and familiar part of HF behaviour.

At the same time, Faraday rotation is only one member of the fading family. Multipath interference, mode structure, tilt, focusing and defocusing, angle-of-arrival changes, skip effects, and noise environment also contribute to what operators hear [3][6].

So the position taken here is:

**Faraday rotation is part of the explanation for what operators observe, but HF fading and HF performance are never reduced to one mechanism alone.**

That is the way the channel behaves.

---

## 6. Why A Mixed-Polarisation Antenna Can Matter

This is where the practical antenna question becomes interesting.

A conventional horizontal antenna mainly responds to the horizontal component of the arriving field. If the incoming wave happens, at that moment, to be arriving with a stronger vertical component, or if part of the useful energy is arriving on a component the antenna couples to poorly, the received signal can dip.

An antenna with both horizontal and vertical response is not immune to fading. But it does have the possibility of coupling to **some useful part** of what the ionosphere is delivering at that moment.

That is why the description “diversity-like” is reasonable, provided it is used carefully.

The NKO is not a classical switched diversity system. It does not have independent receiving channels and a combiner. What it appears to be is a **single structure with mixed horizontal and vertical radiation and reception characteristics**, together with its own amplitude and phase relationships between the long arm, the short arm, and the radiating feedline section. Those relationships shape the total field the antenna launches and the way it responds to arriving fields.

That can matter because the ionosphere does not usually deliver a single clean, fixed-polarisation signal. It delivers a changing mix.

So the working position is:

**The NKO may, on some paths and at some times, weight the available arrival components more favourably than a conventional horizontal antenna, and therefore reduce the depth or frequency of the worst fades.**

That is not a dramatic claim. It is simply a practical statement about how a mixed-response antenna may behave in a mixed-response channel.

The ITU has long recognised that polarisation diversity can reduce fading and distortion on HF systems [5]. That does not prove that NKO must do so in every installation. It does show that the general mechanism is well grounded.

---

## 7. Why NEC May Undervalue NKO On Air

This leads to the main point of the paper.

NEC gives a static description. HF contacts take place in a dynamic channel.

A static pattern plot naturally rewards:

- peak gain in a chosen direction
- clean feedpoint behaviour
- a pattern that looks efficient in one snapshot
- polarisation purity, if the user is thinking in those terms

A real HF path often rewards additional things:

- better coupling to a changing mix of arrival components
- less severe deep fades
- more stable copy over time
- better performance at the bottom of the fading distribution, not only at the top

That is the distinction between **peak gain** and **fade-floor performance**.

If NKO is doing something useful in practice, it may not appear mainly as “several dB more gain on the plot.” It may appear as:

- fewer deep nulls
- shorter bad periods
- better preservation of speech consonants
- higher digital decode success
- better copy when conditions are marginal rather than when they are easy

This is one reason experienced operators sometimes report that a modest-looking antenna performs unusually well when the band is not behaving itself. The antenna may not be winning the static gain contest. It may simply be better matched to the way the real path misbehaves.

---

## 8. There Are Also Non-Ionospheric Reasons NEC And Reality Differ

Not every difference between model and practice comes from the sky.

If the NKO in use differs from the NKO in the model, the cause may be partly or wholly local.

Possible reasons include:

- the choke not providing the assumed common-mode boundary
- the feedline routing in the real installation differing from the model
- nearby gutters, masts, roofs, trees, fences, or wiring altering current distribution
- the real ground being very different from the assumed ground constants
- segmentation or geometry choices in the NEC model being too coarse
- the current on the feedline in reality being larger or smaller than the model predicts
- local noise having a strong polarisation preference, especially man-made noise which often tends to be vertically polarised [3]

That last point matters.

A stronger vertical component may help on some skywave paths. It may also raise noise at some suburban sites. So any realistic evaluation of NKO should separate:

- **field strength**
- **signal-to-noise ratio**
- **intelligibility**
- **fade-depth statistics**

Those are related, but they are not identical.

An antenna that is 2 S-points louder but also 2 S-points noisier has not necessarily improved communication. An antenna that keeps speech detail readable during the worst fades may be the better antenna even if its average meter reading is less dramatic.

---

## 9. The Specific NKO Position

The most defensible form of the NKO positioncompared to NEC, as matters presently stand, is this:

1. The NKO is a three-conductor radiating system consisting of the long arm, the short arm, and a defined radiating section of feedline above the 1:1 choke.

2. That structure produces a mix of horizontal and vertical radiation and reception, with band-dependent amplitude and phase relationships.

3. Because HF propagation commonly involves changing polarisation, changing angle of arrival, and multipath interference, a mixed-response antenna can sometimes couple more favourably to the less-impaired arrival component than a conventional horizontal antenna.

4. Therefore the NKO may show a **real on-air advantage** that appears mainly as reduced fade severity, improved intelligibility, or better decode robustness, rather than as a simple fixed-gain increase.

5. NEC can help with points 1 and 2. It cannot directly evaluate point 3, and therefore it cannot by itself settle point 4.

That is the position advanced here.

It is cautious, but it is also testable.

---

## 10. What We Still Do Not Know

There are still unknowns, and they should be stated plainly.

We do not yet have full measured data for:

- the NKO’s exact horizontal/vertical amplitude ratio on each band
- the phase relationship between those components in the far field
- how those relationships change with feedline length, height, or installation geometry
- whether the observed advantage comes more from polarisation behaviour, angle-of-arrival behaviour, current balance, noise behaviour, or some combination of them

That matters because the vertical feedline section is one physical length serving multiple bands. Its current distribution and radiating contribution will not be the same on 80 m, 40 m, 20 m, and 10 m. It is entirely plausible that NKO is most effective on some bands and less so on others.

That does not weaken the position. It simply identifies where the present investigation honestly stands and where further measurement would be useful.

---

## 11. What NEC Can Still Tell Us About NKO

Used properly, NEC still has substantial value here.

It can help answer questions such as:

- Is the feedline section actually carrying common-mode current in the model?
- How much does the current distribution change if the choke location changes?
- What happens to the elevation pattern when the feedline section is included versus excluded?
- How large are the horizontal and vertical field components in the main directions of interest?
- How sensitive is the pattern to feedline length, arm ratio, height, and slope?
- Is the model stable under segmentation changes, or are the results moving around too much to trust?

These are worthwhile questions. NEC is well suited to them [1].

What NEC does not provide, from that static answer alone, is a full account of how the antenna will behave over time on a live ionospheric path with real fading.

---

## 12. How NKO Should Be Evaluated

If the practical claim is that NKO performs better on air than a static model alone would suggest, then the evaluation should be designed to examine exactly that.

A serious test programme should include:

### A. Fast switching against a reference antenna
Compare NKO against a conventional reference antenna over the same path with switching intervals short enough that propagation has not changed much between samples.

### B. Long observation periods
Short A/B tests can be misleading. The benefit, if real, is likely to be statistical and may show up mainly during the worst parts of the fading cycle.

### C. Fade-depth statistics
Do not look only at average signal. Record minimum signal, fade duration, and time-below-threshold.

### D. SNR and intelligibility
Voice readability and digital decode success may matter more than raw S-meter differences.

### E. Multiple paths
A single path can flatter or hide any antenna. Different distances, azimuths, and times of day are needed.

### F. Noise observations
If one antenna hears more urban noise, that must be separated from any propagation advantage.

### G. Model correlation
Use NEC to predict the static ingredients — current distribution, angle, and H/V balance — and then see which measured outcomes correlate with them.

That is how the subject moves from “interesting observation” toward “supported engineering position”.

---

## 13. Bottom Line

The most useful single statement is this:

> NEC can model the NKO as an antenna, but HF performance is determined by the antenna operating inside a real, time-varying propagation channel and a real installation. The NKO may therefore show practical advantages on air that are not fully expressed in a static NEC comparison.

And the corresponding NKO position is:

> The plausible value of the NKO is not simply extra gain. It is that its mixed horizontal/vertical response and conductor phase relationships may, on some real HF paths, couple more favourably to the less-impaired arrival components and thereby improve fade-floor performance, intelligibility, or decode reliability.

That is not presented here as a slogan or a sales claim.

It is presented as a practical reading of how HF behaves, how NEC behaves, and how the NKO has been observed to behave.

---

## 14. Summary — The One Page Version

- NEC is a very useful antenna modeller, and it models the antenna and its local electromagnetic environment well [1].

- Real HF communication takes place through a time-varying ionosphere that can change the wave’s path, delay, angle of arrival, and polarisation [2][3][6].

- Faraday rotation is real and important, but it is only one contributor to fading. Multipath, ordinary and extraordinary modes, skip effects, TIDs, focusing and defocusing, and local noise also matter [2][3][6].

- The NKO is best regarded as a mixed-response antenna whose horizontal/vertical balance and conductor phase relationships can, on some paths, reduce the depth or frequency of the worst fades.

- That does not make it a magical antenna, nor a classical diversity receiver. It means only that a hybrid response can sometimes be more useful on a real HF path than a static single-polarisation model suggests.

- NEC may therefore undervalue NKO if the practical advantage appears mainly as better fade-floor performance, better intelligibility, or better digital robustness rather than as a simple static gain increase.

- At the same time, some NEC-versus-reality disagreement may come from ordinary modelling issues such as ground assumptions, segmentation, feedline routing, choke effectiveness, and nearby structures [1].

- The correct approach is not to discard NEC. It is to use NEC for the part it can do, and measurement over real paths for the part that lies beyond it.

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

