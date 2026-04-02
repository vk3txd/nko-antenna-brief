# NKO Antenna: Soil Interaction, Ground Effects, and System Behaviour

## Abstract

This document explores how soil properties and ground conductivity may influence the behaviour of the NKO antenna.

Unlike conventional wire antennas, the NKO operates as a 3-wire hybrid system incorporating both horizontal radiating elements and a top-fed vertical radiating feedline component.

This combination introduces multiple mechanisms of ground effects, affecting radiation pattern, efficiency, and propagation behaviour.

Fixed performance claims are not appropriate. Results depend on factors such as installation height, feedline routing, nearby structures, and actual ground conductivity.

---

## 1. Introduction

The NKO antenna is different to a traditional off-centre-fed (OCF) antenna because the top-fed coax shield between the 4:1 Unun and the 1:1 balun radiates and is part of the antenna system. This creates a multi-conductor structure comprising:

- Long arm (horizontal)
- Short arm (horizontal)
- Feedline shield (vertical/common-mode)

This results in a hybrid antenna system with both horizontal and vertical radiation characteristics.

Ground interaction therefore becomes more complex than in conventional antennas.

**Of special note** is that the vertical coax section has its highest current at the apex, at the feedpoint and high in the air, so it behaves more like an elevated top-fed radiator and should be considered that way rather than a ground mounted vertical. This reduces the interaction with ground and reliance on it. At the same time we believe it makes the NKO vertical coax more effective than a ground mounted vertical.

---

## 2. Ground Interaction Mechanisms

At HF, the ground is part of the antenna system whether we like it or not.

Some of the signal leaving the antenna goes straight out, and some interacts with the ground. The two combine in the air, which changes the radiation pattern, especially the takeoff angle.

How well the ground conducts electricity (salt water, salt pans vs wet soil vs dry rock, for example) affects how strong this interaction is. Good ground acts more like a reflector, helping energy launch at useful low angles and reinforcing the signal. 

Poor ground tends to absorb energy instead, weakening the signal and reducing efficiency.

| Ground Type              | Conductivity        | Vertical Efficiency | Low-Angle Radiation | Low-angle usefulness (typical) | NKO Behaviour |
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

Horizontal antennas (like dipoles and OCFs) don’t just radiate into free space — they also interact with the ground below them.

Part of the signal goes straight out, and part of it bounces off the ground, and part of it is absorbed by ground. The radiated and reflected signals combine in the air, which shapes where the signal goes (angle etc), especially the takeoff angle.

Because of this, the ground affects:

- Takeoff angle (how much energy goes out and where - low vs high)
- Pattern shape
- Effective signal strength, especially when the antenna is low to the ground

In simple terms, the ground acts a bit like a lossy reflector. Good ground helps reinforce useful radiation, while poor ground weakens it.

---

### 2.2 Vertical Feedline Components (Feedline Radiation)

The vertical section has the maximum current highest near the feedpoint (apex) and decreases toward the lower portion of the coax. As a result, radiation is concentrated in the upper section of the vertical run.

This behaviour is similar to a top-fed or “inverted” monopole, where the main radiation occurs away from the ground rather than at the base. The effect becomes stronger when the vertical section approaches a significant fraction of a wavelength, such as on 20 m.

An important consequence is that the NKO’s vertical radiation component is likely less dependent on ground conductivity than a conventional ground-mounted vertical. Because the region of strongest current is elevated, ground losses are reduced while low-angle radiation is still supported.

The end result is that the vertical section of coax will be less affected by ground that a simple 1/4 wave vertical mounted near ground.

However and to a lesser degree than a ground mounted vertical there are still effects;

- Ground still forms part of the current return path though to a lesser degree
- Conductivity directly affects radiation efficiency
- Poor ground increases resistive loss
- High conductivity enhances low-angle radiation

These points are consistent with observations that NKO performance from average farmland is often very good, suggesting that extremely high ground conductivity is not required for effective operation.

---

## 3. Combined Behaviour in the NKO

The NKO combines both interaction mechanisms:

| Component | Ground Interaction Type | Primary Effect |
|----------|------------------------|---------------|
| Horizontal arms | Reflection / boundary interaction | Pattern shaping, takeoff angle |
| Feedline (vertical) | Elevated vertical radiator interacting with ground and surroundings | Efficiency, low-angle radiation |

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
On 80/40 m, soil still matters strongly, especially because the whole system is closer to the ground in wavelength terms and the horizontal section remains strongly ground-influenced;

### 20 m and above
On 20 m, the vertical/feedline section may become a more effective radiator in its own right, but because its current maximum is elevated, its behaviour is shaped increasingly by geometry and phase relationships, not just soil conductivity.

_Overall; Ground effects cannot be considered independently of installation parameters such as height, feedline routing etc_

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

Ground affects the NKO in two different ways, and this is what sets it apart from more conventional antennas.

- The horizontal wires behave much like a dipole, where the ground mainly shapes the radiation pattern and takeoff angle  
- The vertical feedline behaves more like an elevated vertical radiator, where ground quality affects how efficiently it contributes to low-angle radiation 

Because both effects are present at the same time:

- On good ground (e.g. salt pan, wet soil), the vertical component works better and adds useful low-angle radiation  
- On poor ground (dry, rocky), the vertical contribution is reduced and the antenna behaves more like a conventional horizontal wire 
- Compared to a simple dipole, the NKO has an additional vertical component that can change with ground conditions  
- Note. Compared to a ground-mounted vertical, the NKO’s vertical component is _less dependent on ground_, because its strongest current is elevated  

In practical terms, the NKO does not rely on ground in a single way — it shifts its behaviour depending on how well the vertical and horizontal parts are supported by the environment.

---

## 8. Key Points

High-conductivity ground such as a salt pan is expected to strengthen the NKO’s vertical/common-mode radiation component, improving low-angle radiation and potentially enhancing path-dependent signal strength and intelligibility, particularly on lower HF bands.

At the same time, ground also affects the horizontal wires by shaping the radiation pattern and takeoff angle, as in any dipole or OCF antenna. The NKO combines both effects, so changes in ground conditions can alter both the radiation pattern and the relative contribution of the vertical and horizontal components.

The magnitude of these effects depends strongly on installation geometry and operating conditions and cannot be reduced to fixed numerical values without modelling or measurement.

---

## References

- Radio Society of Great Britain, *RSGB Radio Communication Handbook*
- ARRL, *The ARRL Antenna Book*
- Davies, K., *Ionospheric Radio*
- ITU-R P.533, *HF Propagation Prediction Method*
- Rappaport, T., *Wireless Communications*
- Proakis, J., *Digital Communications*
