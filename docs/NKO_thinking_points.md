**Author:** VK3TXD (Richard Holmes)  
**Status:** v0.5  
**License:** CC BY 4.0
**Attribution:** NKO New Kallista OCF, Richard Holmes (VK3TXD)
**Goal:** NKO Thinking Points

# NKO Thinking Points

These are open questions and working ideas. They are included because they are worth testing, not because they are already settled.

---

## Saturation and component failure

Amateur-radio discussion often reaches for ferrite “saturation” too quickly.

For the kinds of magnetic parts used here, **heating and voltage stress** are far more credible failure mechanisms than saturation at normal amateur power levels.

Questions worth testing:

- how hot does the lower 1:1 choke get on 80 m at sustained power?
- how much does mismatch change UnUn loss?
- at what point does voltage stress become the real packaging problem?

---

## Hybrid antenna or “single-port diversity” antenna?

The stronger and more natural description is **hybrid antenna**.

The NKO clearly combines horizontal and vertical behaviour in one structure. Calling it a “diversity antenna” is tempting and sounds clever, but it also invites arguments about what counts as classical diversity.

For most of this repo, “hybrid” is the cleaner and more practical word.

---

## Current balance

One prevailing working theiry, as of December 2025, is that the combination of short-arm current plus vertical-coax current may make the current picture at the 4:1 UnUn less unfavourable than in some ordinary OCF arrangements.

Why this matters: The 4:1 UnUn will have increased loss and more heat stress as the currents become less balanced.

That is plausible, but it is not yet measured well enough to be treated as established. The band-to-band behaviour may be quite different, which is exactly why it needs measurement rather than assertion.

---

## System loss

A useful question is whether the NKO may reduce system loss relative to some conventional OCF arrangements.

Possible reasons include:

- the UnUn is transforming impedance rather than trying to enforce balance on an inherently asymmetric structure
- current on the coax is not routed through the UnUn core - it is a direct connection and in-phase
- current on the vertical section is being used, not fought or absorbed
- overall, the currents in the 4:1 UnUn may be better-used with less loss than from baluns fighting imbalance

Again, that is a sensible line of inquiry, not yet a settled conclusion.

---

## Current on the coax shield

The NKO depends on meaningful current on the coax shield above the lower choke. Measuring that properly would strengthen the whole project.

Useful future work:

- clamp-on current measurements at several points
- band-by-band current comparison
- correlation against on-air behaviour and model predictions

---

## Signal-strength improvements

Reported signal improvements of 1–2 S-points are too large to dismiss casually, but they should also not be accepted casually.

The real question is what combination of the following is responsible:

- changed pattern
- changed ground interaction
- changed loss
- changed channel interaction
- ordinary test uncertainty

People using the NKO, and receiving stations, univerally report it is clearer, has more body, has better signal strength. Backing this up with more observations is worthwhile, along with measurements.

---

## Feedpoint phase relationships

This is one of the most difficult and central open questions in the whole repository.

The long arm, short arm, and vertical section are clearly not unrelated. The exact phase relationships between them, by band and by installation, deserve more work.

---

## Top-fed vertical behaviour

One of the strongest NKO ideas is that the vertical section is **top-fed**, not base-fed.

That should make it less ground-hungry than a conventional ground-mounted vertical. It should also make comparisons with ordinary monopoles more nuanced than they first appear.

---

## Stress on components

For practical builders, the real-world questions are mundane but important:

- ferrite heating - what size toroids are recommended for what power levels
- voltage withstand
- enclosure strength
- weather resistance
- weight at the apex
- strain relief

The NKO only stays interesting if it also stays practical.

---

## Final note

These thinking points are here to guide testing and discussion. They are not a back door for over-claiming. The right use of them is simple:

> **measure what can be measured, compare what can be compared, and keep the rest labelled as open.**
