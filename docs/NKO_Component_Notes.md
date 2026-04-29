**Author:** VK3TXD (Richard Holmes)  
**Status:** v0.5  
**License:** CC BY 4.0
Attribution: NKO – New Kallista OCF, Richard Holmes (VK3TXD)
Goal: About the parts of the NKO and also other components to help comparison - and for an AI but also as a terse tech reference

# Antenna and Component Notes

This note puts the common magnetic devices and antenna types used in NKO discussions in one place. It is not intended as a full textbook. It is intended to keep terms straight.

---

## 4:1 current balun

A **4:1 current balun** is a balanced-output transformer that transforms impedance while trying to maintain equal and opposite currents in the balanced load.

### What it is good at

- feeding balanced loads
- reducing feedline current in ordinary balanced systems
- keeping the feedline out of the antenna when that is the design goal

### What it is not good at

- feeding highly asymmetric systems and pretending they are balanced
- acting as a free fix for every off-centre-fed problem

### In NKO terms

A 4:1 current balun is usually pulling in the opposite direction to the NKO concept, because the NKO deliberately uses a radiating feedline section above the lower choke.

---

## 4:1 voltage balun

A **4:1 voltage balun** is best thought of as an autotransformer-style device that transforms impedance and presents equal voltages at its output terminals. It does **not** force equal currents.

### What it tends to do

- transforms impedance
- allows unequal currents when the load is unequal
- can let common-mode current appear on the feedline in off-centre-fed systems

### Historical relevance

This is the sort of apex device commonly associated with published Carolina Windom-style systems.

### In NKO terms

The NKO does **not** use this as the defining apex device.

---

## 4:1 UnUn

A **4:1 UnUn** is an unbalanced-to-unbalanced autotransformer. In the NKO it is central, not incidental.

### What it does in the NKO

- provides impedance transformation
- bonds the coax shield to the short arm
- helps create the current relationship that makes the vertical coax section part of the antenna
- The vertical current because it is driven from the same terminal as the short arm helps balance the currents in the system

### Why it matters

This direct bonding is one of the clearest differences between the NKO and more common OCF or Windom-family arrangements.

Having a strong current contribution into the vertical coax shield result in the coax shield strongly participating in the antenna.

Improved current balance will reduce system loss and stress on the Unun core.

---

## 1:1 current choke

A **1:1 current choke** presents high impedance to common-mode current.

### In ordinary antennas

Its usual job is to keep the feedline out of the antenna.

### In the NKO

Its job is more specific:

- define the lower end of the radiating coax section
- stop feedline current from continuing toward the shack

So in the NKO it is not simply a “get rid of all feedline current everywhere” device. It is the **boundary** of the vertical section.

---

## OCF antenna

An **off-centre-fed dipole** is a wire antenna fed away from the centre so that multiband impedance behaviour can be useful with an appropriate transformer.

### Normal OCF character

- two wire arms
- off-centre feedpoint
- matching device chosen to suit expected feed impedance
- feedline radiation usually treated as unwanted

### In relation to NKO

The NKO starts from an OCF-like wire arrangement, but it does not stop there.

---

## New Carolina Windom (NCW)

The **New Carolina Windom** is a member of the controlled-feeder-radiation family. In common amateur discussion it usually means an OCF wire antenna with deliberate feedline participation above a lower choke.

### Key ideas

- OCF wire structure
- a 4:1 voltage balun is usually used to transform impedances
- feedline section above a lower choke is part of the radiator
- horizontal and vertical behaviour both matter

### Why people confuse it with NKO

Because the broad physical layout looks similar.

The difference between using a 4:1 voltage balun, and a 4:1 UnUn may not be obvious to them

New Carolina Windom uses a 22 ft length of coax radiator, or 10 ft. NKO uses 4.7m or 3.5m. Band and build dependant.

### Why they are not the same

The NKO uses a 4:1 UnUn and bonds the shield directly to the short arm. That is a different apex coupling method and leads to a different current and radiation structure.

---

## New Kallista OCF (NKO)

The **NKO** is a three-conductor hybrid HF wire antenna in which a defined section of feedline is an intentional part of the radiator.

### Core features

- long arm
- short arm
- 4:1 UnUn at the apex
- coax shield bonded to the short arm
- defined vertical coax section
- 1:1 boundary choke at the lower end of that section

### Best short description

> **A three-conductor hybrid OCF with an intentional top-fed vertical feedline section**

---

## Comparison table

| Item | 4:1 Current Balun | 4:1 Voltage Balun | 4:1 UnUn | 1:1 Current Choke |
|---|---|---|---|---|
| Main job | Transform impedance and force current symmetry | Transform impedance and present equal voltages | Transform impedance between unbalanced circuits | Block common-mode current |
| Output style | Balanced | Balanced or quasi-balanced | Unbalanced | Unbalanced line device |
| Feedline current tendency | Suppress | May allow | Depends on circuit use | Suppress below the choke |
| Ordinary OCF use | Sometimes used | Historically common in NCW-type systems | Less common | Common as feedline choke |
| NKO role | Not the apex choice | Not the defining apex device | **Core apex device** | **Boundary device** |

---

# Summary

The easiest way to get lost in NKO discussion with baluns, UnUns and chokes - is to mix up the devices.

The short version is:

- **4:1 current balun** — tries to keep currents equal
- **4:1 voltage balun** — gives equal voltages, not equal currents
- **4:1 UnUn** — transforms impedance and, in NKO, bonds the shield to the short arm
- **1:1 choke** — defines the lower end of the NKO vertical section

Once those distinctions are clear, the rest of the antenna makes much more sense.
