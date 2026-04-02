# NKO Antenna: Soil Interaction, Ground Effects, and System Behaviour

## Abstract

This document presents a structured engineering analysis of how soil properties and ground conductivity influence the behaviour of the NKO antenna.

Unlike conventional wire antennas, the NKO operates as a hybrid system incorporating both horizontal radiating elements and a vertical feedline component.

This combination introduces multiple mechanisms of ground interaction, affecting radiation pattern, efficiency, and propagation behaviour. The analysis focuses on physical mechanisms and observed trends rather than fixed performance claims.

---

## 1. Introduction

The NKO antenna departs from traditional off-centre-fed (OCF) designs by allowing the feedline to participate in the radiating system. This creates a multi-conductor structure comprising:

- Long arm (horizontal)
- Short arm (horizontal)
- Feedline shield (vertical/common-mode)

This configuration results in a hybrid antenna system exhibiting both horizontal and vertical radiation characteristics. Ground interaction therefore becomes more complex than in conventional antennas.

---

## 2. Ground Interaction Mechanisms

### 2.1 Horizontal Components

Horizontal antenna elements interact with ground primarily through boundary effects:

- Reflection at the الأرض–air interface
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

---

## 6. Geometry Dependence

The NKO is highly sensitive to installation geometry:

- Apex height
- Arm lengths and ratio
- Vertical feedline length
- Choke position
- Feedline routing
- Local environment

Ground effects cannot be considered independently of these parameters.

---

## 7. Interaction with Propagation

HF propagation introduces additional effects:

- Multipath propagation
- Frequency-selective fading
- Polarisation rotation

Small changes in radiation characteristics can produce:

- Significant signal strength variation
- Changes in intelligibility
- Altered fading behaviour

The antenna therefore forms part of the effective propagation channel.

---

## 8. Practical Implications

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

## 9. Installation Considerations

To maintain intended NKO behaviour:

- Preserve vertical feedline section
- Position choke appropriately (not at feedpoint)
- Avoid early grounding of feedline
- Maintain consistent geometry

---

## 10. Summary

Ground conductivity influences the NKO through two mechanisms:

1. Horizontal interaction (reflection and pattern shaping)
2. Vertical interaction (current flow and loss)

The NKO combines both, resulting in:

- Increased environmental sensitivity
- Hybrid radiation behaviour
- Context-dependent performance

---

## 11. Key Statement

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
