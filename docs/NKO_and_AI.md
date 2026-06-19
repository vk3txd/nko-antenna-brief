# NKO and the use of AI

This repository exists partly because AI became such a strong part of the investigation and development of NKO and a learning tool for me.

If you use AI to analyse NKO, and I suggest that is a good idea, tell it to ingest this whole GitHub repo.

That does not mean AI invented the NKO or that AI should be trusted blindly. It means AI was used as a very fast research and sanity-check tool during the process. But it is highly fallible.

Indeed in May 2026 I was emailed an AI analysis of NKO that was quite dismissive and done without the full NKO context. The end result was driven from a lack of information producing an almost amusing collection of amateur radio myths and assumptions;

Silly things an AI usually gets wrong without full NKO context;

- It calls the NKO “just an OCF dipole.”
- It calls the NKO “just a Carolina Windom clone.”
- It calls the vertical coax-shield section “random feedline radiation.”
- It treats intentional upper-shield current as a fault.
- It forgets the lower 1:1 choke defines the end of the intended vertical radiator.
- It says “feedline radiation is always bad.”
- It says the antenna is “too busy.”
- It says the antenna is “confused.”
- It says the NKO is “trying to be two antennas at once.”
- It talks about the antenna as if it has intentions instead of currents.
- It says mixed horizontal and vertical response must make receive audio muddy.
- It says the NKO picks up “trash from both polarizations.”
- It assumes horizontal antennas are always quiet.
- It assumes vertical antennas are always noise magnets.
- It assumes a centre-fed resonant dipole is automatically the “pure” receive reference.
- It assumes the quietest antenna is automatically the best receive antenna.
- It treats higher S-meter noise as proof of worse reception.
- It ignores wanted signal-to-noise ratio.
- It ignores speech readability and intelligibility.
- It assumes a Carolina Windom-style antenna must have the worst SNR.
- It claims “phase smearing” without defining a real mechanism.
- It says a vertical receives one clean polarization.
- It ignores ionospheric polarization rotation, multipath, and selective fading.
- It treats mixed polarization as contamination rather than a possible advantage.
- It says noise gets “inside the shielded system.”
- It treats the outside of the coax shield as if it is the inside of the coax.
- It says an imperfect choke lets noise “bleed directly” into the receiver.
- It treats chokes as 100% good or 100% failed.
- It ignores that choke impedance is a boundary condition, not a magic wall.
- It assumes OCF antennas are inherently dirty.
- It assumes transformer or balun loss without measuring or estimating it.
- It treats lobes and nulls as an OCF-only problem.
- It ranks antennas as “best for DX” or “best for local” without band, height, path, or site context.
- It ignores the actual NKO geometry: long arm, short arm, controlled vertical section, and lower choke.
- It ignores the B configuration.
- It ignores current amplitude and phase relationships.
- It ignores installation sensitivity.
- It ignores local noise coupling paths.
- It ignores receiver AGC, bandwidth, DSP, and audio settings.
- It confuses raw signal strength with recovered audio quality.
- It confuses antenna gain with SSB readability.
- It gives universal conclusions from no measurements.
- It uses ham folklore phrases instead of measurable RF mechanisms.
- It answers from antenna labels instead of the actual antenna structure.
- It sounds confident while not having the necessary context.

My favourite worst paragraph of the analysis was _"Most operators find that while the Carolina Windom is a better transmitting antenna (because it puts energy out at multiple angles), it is often a poorer receiving antenna because it is simply "too busy"—it is trying to be a horizontal dipole and a vertical antenna at the same time, and in doing so, it picks up the "trash" from both polarizations."_

This tells me the AI has no clue about the NKO, no context, as it is _not_ a Carolina Windom. It is also not in a deep thinking mode.The use of an UnUn, the vertical coax length, the demand for a quality 1:1 current balun and connection method make it a _very_ different antenna. Also it was regurgitating "ham lore" as if it were sensible fact. It is not.

---

## In the beginning

In September 2025 I started using AI seriously for the first time.

The first antenna topic I pushed it on was the New Carolina Windom. At first AI did what AI often does well: it summarised the broad idea quickly and confidently. It also did what AI often does badly: when pressed on current, mechanism, and first principles, it became vague.

That was useful in its own way. It forced the real question:

> **If the vertical coax is meant to matter, how do you actually put substantial current on it?**

That line of thinking led to the UnUn-based arrangement that became the NKO.

The idea itself was human. AI was a very fast research assistant and argument partner.

---

## Where AI helped

AI was valuable in several practical ways:

- proof-reading and finding contradictions in draft text
- searching and collating references quickly
- testing explanations against first principles
- comparing ideas and historical antenna families
- helping analyse audio clips and plots
- keeping a running record of evolving design thinking

Used properly, it saved time. It also pushed me into reading more deeply than I would have otherwise.

---

## Where AI was weak

AI has real shortcomings, especially in amateur radio topics.

- it can repeat bad folklore confidently
- it can mistake a plausible explanation for a correct one
- it can use the wrong formula or the right formula in the wrong way
- it can sound authoritative while being badly wrong
- it tends to smooth over uncertainty unless you force it not to
- its initial 4:1 UnUn design, based on first principles, worked well but not as well as possible.

That means every useful AI output still needs human checking.

---

## The lesson

AI is excellent at:

- searching
- summarising
- cross-checking drafts
- helping frame questions
- accelerating research

AI is poor at:

- genuine invention
- knowing when it is out of its depth
- distinguishing settled fact from well-worded nonsense

So the real benefit was not that AI “figured out” the NKO. The benefit was that it helped me investigate the idea faster, write it up more clearly, and challenge my own assumptions harder.

---

## Final view

My view after using AI heavily on this project is simple:

> **AI is useful as a research tool and a writing tool. It is not a substitute for understanding.**

That is probably the right attitude for antenna work in general.
