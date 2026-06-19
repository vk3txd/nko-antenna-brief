# NKO Antenna – Common Misconceptions

This file addresses the objections that come up most often when people first see the NKO.

2026/06/19 - The Myths section at the end has been added.

---

## 1. “Using an UnUn with OCF arms is incorrect.”

We use a Balun because that is the accepted best practice. Coax is unbalanced, and the OCF is unbalanced. So using a balun that expects balance at the load is straight away wrong!

So back to basics; a balun is ideally used to connect a balanced antenna to an unbalanced feedline (coax). Unbalanced loads present unbalanced currents and voltages to a balun which may not be well handled causing loss and heating.

The NKO is not trying to be a conventional OCF dipole. It is a three-conductor hybrid structure in which the feedline is intentionally part of the system. In that context, the UnUn is not being used to pretend the load is balanced. It is being used to transform impedance and bond the shield to the short arm.

My experience is that an AI will say that _only_ a 4:1 current balun may be used with an OCF - and anything else won't work with all sorts of dire consequences. The solution is to give the AI the link to this repo and tell it to analyse it properly.

---

## 2. “Feedline radiation is always a fault.”

In ordinary antenna work, feedline radiation is usually unwanted. Worst case it can cause a transceiver to rest or have other issues.

In the NKO, a defined section of feedline radiation is intentional.

The important distinction is control. The NKO uses a lower 1:1 choke to define the end of the radiating coax section and to keep the rest of the feedline out of the antenna.

---

## 3. “A current balun is required to force balance.”

Only if forcing balance is the design goal. If the load is unbalanced then the balun is not being used in its optimum application.

The NKO does not aim to force equal currents into two unequal arms and call that success. It uses a different coupling method and a different antenna structure.

---

## 4. “This is just a Carolina Windom.”

It is in the same broad family of ideas, but it is not the same antenna.

The NKO differs in the use of a 4:1 UnUn, in the direct bonding of shield to short arm, and in the way the radiating coax section is defined and discussed.

---

## 5. “Common-mode current is loss.”

Common-mode current can be associated with loss and trouble. It is not automatically loss.

In the NKO, common-mode current on the defined vertical coax section is part of the intended antenna behaviour. Loss depends on where the current flows and what it is doing, not on the phrase alone.

---

## 6. “This is an EFHW variant.”

No. The NKO is not an end-fed antenna.

It is a three-conductor hybrid structure with an off-centre-fed wire arrangement plus a defined vertical feedline section.

---

## 7. “The feedline is just a parasitic element.”

Not in the NKO. The coax shield is directly connected to the short OCF arm. It is not parasitic.

The feedline above the lower choke is a defined and intentional part of the radiator. That is built into the antenna concept.

---

## 8. “The 1:1 choke is there to eliminate all common-mode current.”

Not quite.

In the NKO, the lower 1:1 choke is there to stop common-mode current continuing beyond the intended vertical section. 

Importantly, it defines the boundary of the radiator. It sets the length of coax that radiates.

---

## 9. “The antenna behaves like a conventional dipole.”

No. It may share some wire dimensions with OCF antennas, but it should not be treated as an ordinary two-wire dipole.

The long arm, short arm, and vertical coax section form one coupled structure.

---

## 10. “Any reported improvement must just be more signal.”

Signal strength may be part of the story, but it is unlikely to be the whole story.

Some of the reports point to **clarity**, **readability**, and **copy on familiar stations**, which suggests that path interaction and audio-related fading effects may matter as well.

That remains a working explanation, not a final proof.

---

## Short version

The NKO is easiest to misunderstand when it is judged as though it were trying to be a normal OCF dipole.

It is not.

Treat it as a three-conductor hybrid antenna first. Most of the apparent contradictions disappear at that point.

---

## Myths and folklore traps in generic AI antenna analysis

The following table captures common amateur-radio folklore claims that can appear in generic AI antenna analysis.

Some contain a grain of truth, but they become misleading when used to dismiss the NKO without considering its actual geometry: 

- a defined upper coax-shield radiator, 
- the B-configuration relationship between the short arm and shield, and the phase relationship between them,
- and a lower choke that bounds the radiating section.

| Folklore claim / myth | Why it is misleading | Better NKO-aware framing |
|---|---|---|
| A resonant dipole is the gold standard for purity. | A resonant dipole is simple, efficient, and predictable, but it is not magically immune to local noise, poor feed practice, nearby metalwork, or installation effects. | A well-installed centre-fed dipole is a useful reference antenna, not an absolute purity standard. |
| Horizontal antennas are quiet; vertical antennas are noise magnets. | Often observed in suburban environments, but not a law. Noise pickup depends on location, height, local coupling, common-mode paths, and wanted-signal strength. | Compare useful signal-to-noise ratio and intelligibility, not antenna stereotypes. |
| Off-centre-fed dipoles are inherently dirty. | OCF antennas are more prone to common-mode current because of asymmetry, but that does not make every OCF poor. Transformer design, choking, and installation matter. | A standard OCF needs common-mode control. The NKO deliberately defines part of the common-mode path as a radiator. |
| Feedline radiation is always bad. | Uncontrolled feedline radiation is bad. Controlled current on a defined conductor can be part of the antenna. | In the NKO, the upper coax shield section is intentionally part of the radiator. The lower choke defines where that section ends. |
| Common-mode current means a fault. | In ordinary feedline practice, unwanted common-mode current is a fault. In the NKO, common-mode current above the lower choke is part of the intended radiator. | Common-mode current above the choke can be intentional. Common-mode current below the choke is the unwanted part. |
| A Windom-style antenna is trying to be two antennas at once. | This anthropomorphises the antenna and replaces analysis with imagery. An antenna is not “confused”; it has a current distribution. | The useful question is the amplitude and phase of current on the long arm, short arm, and controlled vertical section. |
| The antenna is “too busy.” | “Too busy” is not an RF mechanism. It is a sticky phrase, but it does not identify a measurable defect. | Complex current distribution may help or hurt. The result must be judged by pattern, noise, and measured readability. |
| Mixed horizontal and vertical response makes receive audio muddy. | Mixed polarization is not inherently bad. On HF, received skywave polarization is often rotated, split, and time-varying. | Mixed response can behave like useful diversity on some paths, or increase local-noise pickup on others. |
| Phase smearing explains poor audio. | This is usually hand-waving unless tied to a specific mechanism such as multipath delay, selective fading, AGC behaviour, DSP artefacts, or pattern nulls. | If audio is worse, measure SNR, spectral notches, fading, AGC behaviour, and speech-band energy. |
| A vertical receives one clean polarization. | HF skywave does not arrive as a neat fixed polarization. Faraday rotation, O/X modes, multipath, and arrival angle all complicate received polarization. | A vertical has a different response pattern and polarization tendency, not a monopoly on a clean signal type. |
| The antenna picks up trash from both polarizations. | This frames mixed response as inherently contaminated and ignores that wanted HF energy may also arrive in mixed or rotating polarization. | The real question is whether the controlled vertical component improves wanted signal more than it increases local noise. |
| Noise gets inside the shielded system. | Poor wording. The outside of the coax shield above the choke is not “inside” the coax; it is the outer conductor being used as part of the antenna. | Above the lower choke, the outside of the shield is a defined receiving/radiating conductor. Below the choke, common-mode current should be suppressed. |
| If the choke is not 100%, noise bleeds directly into the receiver. | Chokes are not binary. Poor choking can extend the antenna down the feedline and increase shack coupling, but “bleeds directly into the receiver” is scare language. | Choke quality affects where the common-mode antenna ends and how much installation noise enters the system. |
| A Carolina Windom or NKO must have the worst SNR. | Sometimes it may; sometimes it will not. It depends on band, path, wanted-signal angle, local noise, and installation. | Compare band-by-band and path-by-path using measured SNR and intelligibility. |
| A quieter antenna is automatically the better receive antenna. | A quiet antenna may also be weak on the wanted signal. The useful measure is signal-to-noise ratio and readability, not low noise alone. | The best receive antenna is the one that gives better useful copy on the target path. |
| More S-meter noise means a worse antenna. | A better antenna may hear more of everything: signal and noise. The ratio matters. | Measure wanted signal, noise floor, and speech-band SNR. |
| A multiband antenna is a compromise, therefore worse. | All practical antennas are compromises. A multiband antenna can outperform a single-band reference on a particular path if its pattern and polarization are favourable. | State the actual trade-offs: bandwidth, pattern, loss, complexity, feedline control, and site sensitivity. |
| OCF transformer loss makes the design inefficient. | Transformer loss is real, but it depends on material, core size, winding, impedance, frequency, mismatch, and duty cycle. It should not be used as a vague dismissal. | Treat transformer loss as an engineering item. Measure it or test it thermally. |
| Lobes and nulls are an OCF problem. | Lobes and nulls occur in any electrically long antenna, including doublets, long dipoles, and OCFs. | Pattern structure comes from electrical length, height, geometry, and current distribution. |
| A vertical component automatically means better DX. | Lower-angle response can help DX, but only when the resulting pattern, polarization, and noise environment favour the path. | The vertical component may improve some DX paths; it is not an automatic guarantee. |
| A hybrid antenna is usually a poorer receive antenna. | A hybrid structure can be better, worse, or simply different. The statement has no value without band, path, site-noise, and pattern context. | Judge the NKO by measured readability and SNR on the paths of interest. |
| Core saturation is the obvious ferrite risk. | At HF, classic magnetic saturation is often not the first limit. Heating, mismatch, voltage stress, winding loss, and ferrite RF loss usually matter first. | Discuss RF flux stress and thermal behaviour, not scary saturation claims. |

### Short correction

The NKO should not be dismissed using generic “hot feedline” folklore.

Uncontrolled common-mode current is a problem. Controlled current on a defined conductor can be part of the antenna. Mixed horizontal and vertical response is not inherently muddy or confused, especially on HF where received polarization is often rotated and time-varying.

The real questions are:

- what currents flow on the long arm, short arm, and controlled vertical section
- how well the lower choke defines the end of the radiator
- what pattern and polarization mix result
- whether local noise increases more or less than the wanted signal
- what measured readability and speech-band SNR show on the target paths

