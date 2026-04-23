# Distinguishing the NKO from the (New) Carolina Windom

The NKO is often assumed to be “just a Carolina Windom.” That is understandable. At a glance, both antennas have:

- an off-centre-fed wire arrangement
- a 4:1 device at the apex
- a 1:1 choke some distance down the coax
- intentional feedline participation above the choke

That family resemblance is superficially real. The antennas are not, however, the same thing.

---

## The key difference

In the NKO, the apex device is a **4:1 UnUn**, _not_ a 4:1 voltage or curent balun used with the usual published Carolina Windom designs.

That matters because the UnUn does three jobs at once:

- it transforms impedance
- it bonds the coax shield _directly_ to the short arm
- it forces a defined phase relationship between the horizontal and vertical arms (as a result that is often ignored)

This means the vertical coax section is not being excited only as a side-effect of imbalance. It is coupled into the system directly by the connection arrangement itself.

---

## What the NKO does

The NKO is best thought of as a **three-conductor coupled antenna system**:

- long arm
- short arm
- defined vertical coax section

The lower 1:1 choke is used as a **boundary device**. Its job is to define the electrical end of the radiating coax section and keep the rest of the feedline out of the antenna.

That is a more explicit and more tightly defined use of the feedline than the ordinary “feedline happens to radiate” story often told about Windom-family antennas.

---

## Practical differences from the New Carolina Windom

### 1. Apex coupling method

- **NKO:** 4:1 UnUn, shield bonded to short arm
- **NCW (common published form):** typically a 4:1 voltage-type feed arrangement with feedline radiation arising from imbalance

### 2. Role of the feedline

- **NKO:** feedline section is an intentional, bounded part of the radiator
- **NCW:** feedline radiation is part of the idea, but the exact current relationships are less explicitly documented, dependant on balun performance and the impedances of the OCF arms. It is variable

### 3. Lower choke

- **NKO:** the lower 1:1 choke is fundamental to defining the radiator
- **NCW:** "line isolator" is a commonly used term with the NCW with the intention to make the coax above a defined radiator. The lack of documentation makes this unclear

### 4. Documentation

- **NKO:** openly documented and discussed as a developing design brief
- **NCW:** historically associated with commercial products and far less open technical documentation

### 5. Design emphasis

- **NKO:** built around the idea of a three-conductor hybrid structure
- **NCW:** better thought of as the historical “controlled feeder radiation” family from which the NKO takes inspiration

---

## Where they really are similar

To be fair, the two antennas do share some broad family traits:

- both start from an OCF-style wire arrangement
- both use the feedline above a lower choke as part of the radiating structure
- both combine horizontal and vertical behaviour
- both sit in the broader “controlled feeder radiation” family of ideas

So the right statement is not “completely unrelated.” The right statement is:

> **same broad family, different coupling method, different level of definition, and different documentation style**

---

## Why the distinction matters

Calling the NKO “just a Carolina Windom” hides the actual questions worth discussing:

- what current relationship does the UnUn create?
- how strongly is the vertical section driven?
- how does the top-fed vertical section change the pattern?
- how much of the on-air behaviour comes from this particular architecture rather than from the general Windom family?

Those are real engineering questions. They are also the questions that make the NKO worth testing as its own design rather than dismissing it by resemblance.

This was considered an 'issue' in that the New Carolina Windom has a history that I did not want to be associated with. I want the NKO to stand as its own antenna and be considered as such. The use of an UnUn makes the whole antenna behave differently to a New Carolina Windom.

---

## Phase relationship — where NKO and NCW really differ

This is an important difference between the two antennas.

In the NKO the coax shield is connected **directly** to the short OCf arm at the UnUn. They share the same connection point. The vertical coax section and the short arm are driven in phase with each other. The feedpoint introduces no phase offset between the horizontal and vertical components.

In the Carolina Windom the vertical coax section is driven by the **voltage imbalance** across the balun windings — the difference current produced by the long and short arms presenting unequal impedances to the balun. That difference current carries a phase relationship to the horizontal wire currents that depends on the arm impedance ratio, the balun winding characteristics, and the frequency. All of these change across bands and between installations.

So for NCW the magnitude and the phase relationships are highly variable.

The result is a phase relationship between horizontal and vertical components in the Carolina Windom that is **variable, uncontrolled, and unpredictable** — in reality it is _variables stacked on variables_.

On some bands and some installations it may accidentally produce a useful phase relationship. On others it may not. The operator has no way to know which situation they are in.

The NKO does not solve the phase question completely — what the actual phase relationship is by band remains an open measurement question. But the feedpoint is not making the situation worse by introducing uncontrolled phase variation on top of whatever the antenna geometry and propagation already create.

That is a meaningful and practical advantage over the Carolina Windom approach.

---

## Short version

The NKO is **not** unrelated to the Carolina Windom. It is also **not** simply the same antenna with a new name.

A fair description would be:

> **The NKO is a more explicitly defined, openly documented, UnUn-coupled member of the controlled-feeder-radiation family.**
