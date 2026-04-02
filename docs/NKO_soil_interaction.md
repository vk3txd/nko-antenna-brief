# NKO Antenna: Soil Interaction, Ground Effects, and System Behaviour

## Abstract

This document explores how soil properties and ground conductivity may influence the behaviour of the NKO antenna.

Unlike conventional wire antennas, the NKO operates as a 3-wire hybrid system incorporating both horizontal radiating elements and a vertical radiating feedline component.

This combination introduces multiple mechanisms of ground effects, affecting radiation pattern, efficiency, and propagation behaviour.

We can't give fixed performance claimsbecause there are too many other factors; height above ground, feedline routing, nearby structures and actual conductivity of the soil versus what we think it is.

---

## 1. Introduction

The NKO antenna is different to a traditional off-centre-fed (OCF) antenna because the coax between the 4:1 Unun and the 1:1 balun radiates and really is part of the antenna system. This creates a multi-conductor structure comprising:

- Long arm (horizontal)
- Short arm (horizontal)
- Feedline shield (vertical/common-mode)

This results in a hybrid antenna system with both horizontal and vertical radiation characteristics.

Ground interaction therefore becomes more complex than in conventional antennas.

---

## 2. Ground Interaction Mechanisms

At HF, the ground is part of the antenna system whether we like it or not.

Some of the signal leaving the antenna goes straight out, and some interacts with the ground. The two combine in the air, which changes the radiation pattern, especially the takeoff angle.

How well the ground conducts electricity (salt water, salt pans vs wet soil vs dry rock, for example) affects how strong this interaction is. Good ground acts more like a reflector, helping energy launch (or arrive) at useful low angles and reinforcing the signal. 

Poor ground tends to absorb energy instead, weakening the signal and reducing efficiency.

| Ground Type              | Conductivity        | Vertical Efficiency | Low-Angle Radiation | DX Performance (Typical) | NKO Behaviour |
|-------------------------|--------------------|---------------------|---------------------|--------------------------|--------------|
| Salt Pan                | Very high          | Excellent           | Very strong         | Often enhanced           | Strong vertical + horizontal hybrid |
| Coastal (near salt water)| High (effective)  | Very good           | Strong              | Often enhanced           | Strong hybrid, low-angle aided by sea reflection |
| Arable Soil             | Moderate           | Good                | Good                | Typical                  | Balanced hybrid |
| Sandy Soil (dry)        | Low                | Moderate to poor    | Moderate to weak    | Variable                 | Reduced vertical contribution |
| Sandy Soil (wet/saline) | Moderate to high   | Good                | Good to strong      | Often improved           | Improved hybrid behaviour |
| Mineralised Ground (e.g. Golden Triangle) | Variable (often lossy) | Variable            | Variable                | Unpredictable            | Mixed behaviour, potential additional losses |
| Mountain / Rocky Soil   | Very low           | Poor                | Weak                | Often reduced            | Mostly horizontal behaviour |
| Urban / Mixed           | Highly variable    | Variable            | Variable            | Highly variable          | Strongly environment-dependent |

The above is intended to be indicative of what we may expect. Again, same caveats about installation height etc.

### 2.1 Horizontal Components

Horizontal antenna elements interact with ground primarily through boundary effects:

- Interaction at the ground–air boundary (including reflection effects)
- Formation of image currents
- Constructive/destructive interference shaping elevation patterns

Ground properties influence:

- Takeoff angle
- Pattern shape
- Effective gain (especially at low heights)

### 2.2 Vertical Components (Feedline Radiation)

The NKO introduces a vertical radiating element via common-mode current on the feedline:

- Ground forms part of the current return path
- Conductivity directly affects radiation efficiency
- Poor ground increases resistive loss
- High conductivity enhances low-angle radiation

---

## 3. Combined Behaviour in the NKO

The NKO combines both interaction mechanisms:

| Component | Ground Interaction Type | Primary Effect |
|----------|------------------------|---------------|
| Horizontal arms | Reflection / boundary interaction | Pattern shaping, takeoff angle |
| Feedline (vertical) | Current flow / ground return | Efficiency, low-angle radiation |

This results in a coupled system where:

- Radiation pattern is a vector combination of multiple elements
- Polarisation is mixed (horizontal + vertical)
- Performance is highly dependent on environment and geometry

---

## 4. Soil Type Effects

The following table summarises expected qualitative behaviour across common soil types:

| Soil Type | Conductivity | Horizontal Effect | Vertical Effect (Feedline) | Overall NKO Behaviour | Notes |
|----------|-------------|------------------|----------------------------|----------------------|------|
| Salt pan / seawater | Very high | Strong reflection, low-angle reinforcement | Very efficient radiation, minimal loss | Strong hybrid behaviour, enhanced low-angle radiation | Best-case for vertical contribution |
| Wet fertile soil | High | Good reflection, stable pattern | Efficient vertical radiation | Balanced hybrid behaviour | Typical “good” conditions |
| Average soil | Moderate | Moderate reflection | Moderate efficiency | Geometry-dependent | Most common case |
| Dry sandy soil | Low | Weaker reflection | Reduced vertical efficiency | Reduced hybrid effect | Vertical contribution diminished |
| Rocky / arid terrain | Very low | Poor reflection | High loss in vertical component | Behaviour approaches horizontal antenna | Worst-case scenario |
| Urban / mixed | Variable | Unpredictable reflections | Variable efficiency | Highly variable | Structures dominate |

---

## 5. Frequency Dependence

Ground effects vary significantly with frequency:

### 80 m / 40 m
- Strong ground interaction
- Vertical efficiency critical
- Soil conductivity has noticeable impact

### 20 m and above
- Reduced ground influence
- Geometry dominates
- Vertical contribution still present but less sensitive

_Ground effects cannot be considered independently of installation parameters such as height, feedline routing etc_

---

## 6. Practical Implications

### High Conductivity Ground (Salt Pan)

- Strong vertical radiation component
- Improved low-angle radiation
- Enhanced DX potential on lower bands
- Increased likelihood of diversity effects

### Poor Ground (Rocky / Dry)

- Reduced vertical efficiency
- Increased loss
- Behaviour approaches conventional horizontal wire

---

## 7. Summary

Ground conductivity influences the NKO through two mechanisms:

1. Horizontal interaction (reflection and pattern shaping)
2. Vertical interaction (current flow and loss)

The NKO combines both, resulting in:

- Increased environmental sensitivity
  - Soil type will change NKO behaviour more than for a simple dipole or vertical antenna
- Hybrid radiation behaviour
- Context-dependent performance

---

## 8. Key Points

High-conductivity ground such as a salt pan is expected to strengthen the NKO’s vertical/common-mode radiation component, improving low-angle radiation and potentially enhancing path-dependent signal strength and intelligibility, particularly on lower HF bands.

The magnitude of these effects depends strongly on installation geometry and operating conditions and cannot be reduced to fixed numerical values without modelling or measurement.

---

## References

- Radio Society of Great Britain, *RSGB Radio Communication Handbook*
- ARRL, *The ARRL Antenna Book*
- Davies, K., *Ionospheric Radio*
- ITU-R P.533, *HF Propagation Prediction Method*
- Rappaport, T., *Wireless Communications*
- Proakis, J., *Digital Communications*
