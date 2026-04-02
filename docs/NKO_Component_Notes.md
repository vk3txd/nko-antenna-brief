# Antenna and Component Notes

---

## 4:1 Current Balun

- _Definition_ 
  - _4:1_ Indicates an impedance transformation ratio between input and output ports  
  - _Type_ A current balun (Guanella) is a transmission-line transformer that enforces equal and opposite currents at its balanced output terminals  
  - _Purpose_ Connects an unbalanced source to a balanced load while maintaining current symmetry  

- _Function_ Transforms impedance while maintaining current balance  

- _Topology_ Transmission line or bifilar windings on ferrite cores  

- _Electrical Behaviour_
  - _Balance_ Forces equal currents in the two output conductors regardless of load impedance differences  
  - _Common Mode_
    - _Origin_ Arises from load imbalance or impedance mismatch  
    - _Response_ Presents high impedance to common-mode current  
    - _Effect_ Suppresses feedline current by diverting imbalance into the transformer  

- _Performance_ Best (most efficient) with balanced or near-balanced loads  

- _Mismatch Behaviour_
  - _Effect_ Imbalance current is driven into the transformer  
  - _Consequence_ Increased stress on ferrite and reduced efficiency  

- _Loss & Heating_
  - _Loss_ Core loss increases with imbalance and impedance mismatch  
  - _Heating_ Ferrite dissipates imbalance energy as heat  

- _Limitations_
  - _Load Type_ Poor match for highly asymmetric systems  
  - _Frequency_ Choking effectiveness varies with frequency  

- _Interaction_
  - _System Effect_ Reduces coupling between antenna and feedline  

- _Failure Mode_ Loss is driven by load imbalance and impedance mismatch, producing ferrite heating  

- _In NKO Context_ Opposes intended feedline participation  

---

## 4:1 Voltage Balun

- _Definition_ 
  - _4:1_ Indicates an impedance transformation ratio between input and output ports  
  - _Type_ A voltage balun (Ruthroff) is an autotransformer that enforces equal voltages at its output terminals  
  - _Purpose_ Connects an unbalanced source to a balanced load without enforcing current symmetry  

- _Function_ Transforms impedance without controlling current balance  

- _Topology_ Autotransformer-style winding on ferrite  

- _Electrical Behaviour_
  - _Balance_ Does not enforce equal currents in the load  
  - _Common Mode_
    - _Origin_ Arises from unequal currents caused by unequal load impedances  
    - _Mechanism_ Equal voltages applied to unequal impedances produce unequal currents  
    - _Effect_ Difference current flows onto the feedline as common-mode current  

- _Performance_ Handles unbalanced loads more readily than current baluns  

- _Mismatch Behaviour_
  - _Effect_ Imbalance is passed into the antenna system  
  - _Consequence_ Feedline becomes part of the radiating structure  

- _Loss & Heating_
  - _Loss_ Core loss increases with mismatch and current  
  - _Heating_ Heating occurs under high current and imbalance conditions  

- _Limitations_
  - _Control_ Does not suppress feedline current  
  - _Dependency_ Behaviour depends on installation and environment  

- _Interaction_
  - _System Effect_ Couples antenna and feedline behaviour  
  - _Control Method_ Often requires an external choke to limit feedline current  

- _Failure Mode_ Loss is driven by impedance mismatch and circulating current, producing ferrite heating  

- _In NCW Context_ Used with downstream choke to define radiating section  
- _In NKO Context_ Does not provide the required current relationship or phase behaviour  

---

## 4:1 UnUn (Autotransformer)

- _Definition_ 
  - _4:1_ Indicates an impedance transformation ratio between input and output ports  
  - _Type_ An unun is an unbalanced-to-unbalanced autotransformer using a single winding with taps  
  - _Purpose_ Transforms impedance between unbalanced circuits without enforcing current balance  

- _Function_ Provides impedance transformation without isolating currents  

- _Topology_ Single winding with taps on a ferrite core  

- _Electrical Behaviour_
  - _Balance_ Does not enforce current symmetry  
  - _Common Mode_
    - _Origin_ Arises naturally from system geometry and load conditions  
    - _Response_ Does not oppose common-mode current  
    - _Effect_ Allows current to flow onto the feedline as part of the system  

- _Performance_ Handles asymmetric and unbalanced loads effectively  

- _Mismatch Behaviour_
  - _Effect_ Imbalance is passed directly into system currents  
  - _Consequence_ Current distribution is determined by the full antenna system  

- _Loss & Heating_
  - _Loss_ Core loss depends on current, frequency, and impedance mismatch  
  - _Heating_ Heating results from total current rather than suppression mechanisms  

- _Limitations_
  - _Choking_ Provides no inherent suppression of common-mode current  
  - _Dependency_ Strongly dependent on installation and system geometry  

- _Interaction_
  - _System Effect_ Forms part of the total radiating system  
  - _Control Method_ External choking may be used to define current distribution  

- _Failure Mode_ Loss is driven mainly by impedance mismatch and load current, producing heating  

- _In NKO Context_ Enables coupling of feedline and antenna currents, supporting in-phase current addition  

---

## Comparison Table

| Feature | 4:1 Current Balun | 4:1 Voltage Balun | 4:1 UnUn |
|--------|------------------|------------------|----------|
| _Balance Type_ | Current | Voltage | None |
| _Impedance Transform_ | Yes | Yes | Yes |
| _Forces Current Symmetry_ | Yes | No | No |
| _Common Mode Suppression_ | High | Low | None |
| _Feedline Radiation_ | Suppressed | Allowed | Enabled |
| _Best Use Case_ | Balanced antennas | Windom/NCW | End-fed / NKO |
| _Handles Asymmetry_ | Poor | Moderate | Strong |
| _Choking Function_ | Inherent | External required | None |
| _System Interaction_ | Moderate | High | High |
| _System Control_ | High (balance) | Low | System-dependent |
| _Mismatch Handling_ | Dissipates imbalance in core | Passes imbalance to system | Passes imbalance directly |
| _Mismatch Loss Location_ | Core dominant | Core + feedline | System currents |
| _Mismatch Heating_ | Core heating significant | Moderate distributed heating | Current-driven heating |
| _NKO Suitability_ | Poor | Partial | Optimal |

---

## OCF Antenna

- _Definition_
  - _Type_ An off-centre-fed dipole (OCF) is a half-wave wire antenna fed at a point displaced from its electrical centre  
  - _Structure_ Two unequal-length conductors forming a balanced radiating element  
  - _Purpose_ Provides multi-band operation via harmonic resonance and usable feedpoint impedances  

- _Function_ Radiates RF energy as a dipole with an off-centre feedpoint  

- _Topology_ Single wire element with off-centre feed and balun interface  

- _Electrical Behaviour_
  - _Balance_ Intrinsically unbalanced current distribution due to feedpoint offset  
  - _Common Mode_
    - _Origin_ Arises from current imbalance between the two arms  
    - _Response_ Typically suppressed using a current balun or choke  
    - _Effect_ Residual common-mode current may flow on the feedline if not adequately suppressed  

- _Performance_ Provides multi-band coverage with varying impedance and pattern  

- _Mismatch Behaviour_
  - _Effect_ Feedpoint impedance varies widely across bands  
  - _Consequence_ High SWR may occur, increasing system loss  

- _Loss & Heating_
  - _Loss_ Occurs in balun and feedline under mismatch conditions  
  - _Heating_ Balun may dissipate energy under imbalance and mismatch  

- _Limitations_
  - _Pattern_ Multi-lobed radiation patterns with frequency dependence  
  - _Control_ Requires effective choking to manage feedline current  

- _Interaction_
  - _System Effect_ Designed to minimise feedline participation in radiation  

- _Failure Mode_ Loss driven by mismatch and imbalance, producing balun heating and feedline loss  

- _Comparison_ Baseline reference for OCF-derived systems  

---

## New Carolina Windom Antenna (NCW)

- _Definition_
  - _Type_ A variant of the off-centre-fed dipole incorporating feedline radiation  
  - _Structure_ Off-centre-fed wire with a coaxial feedline carrying common-mode current  
  - _Purpose_ Introduces a vertical radiation component by utilising feedline current  

- _Function_ Radiates via both the wire element and a controlled section of feedline  

- _Topology_ Off-centre-fed wire with voltage balun and downstream choke  

- _Electrical Behaviour_
  - _Balance_ Does not enforce current symmetry  
  - _Common Mode_
    - _Origin_ Arises from unequal currents due to voltage-fed structure  
    - _Response_ Allowed to propagate onto the feedline  
    - _Effect_ Feedline becomes part of the radiating system  

- _Performance_ Combines horizontal and vertical radiation components  

- _Mismatch Behaviour_
  - _Effect_ Imbalance and mismatch are passed into the system  
  - _Consequence_ Feedline current and radiation vary with installation  

- _Loss & Heating_
  - _Loss_ Occurs in transformer and system under mismatch  
  - _Heating_ Transformer may dissipate energy under imbalance  

- _Limitations_
  - _Control_ Feedline radiation is only partially controlled  
  - _Dependency_ Performance varies with installation geometry  

- _Interaction_
  - _System Effect_ Feedline is coupled into the radiating system with indeterminate phase relationships
  - _Control Method_ Choke (down feedline) defines the effective radiating feedline section  

- _Failure Mode_ Loss driven by mismatch and uncontrolled current distribution, producing heating and variable radiation  

- _Comparison_ Intermediate between OCF and fully integrated feedline systems  

---

## New Kallista OCF (NKO) Antenna

- _Definition_
  - _Type_ A hybrid wire antenna system integrating the feedline as a radiating conductor  
  - _Structure_ Off-centre-fed wire and coaxial feedline forming a coupled three-conductor system  
  - _Purpose_ Uses controlled feedline current to shape radiation and current distribution  

- _Function_ Radiates via both the wire element and a defined section of feedline  

- _Topology_ Off-centre-fed wire with 4:1 autotransformer (UnUn) and defined feedline section  

- _Electrical Behaviour_
  - _Balance_ Effective balance occurs between long arm and combined short arm plus feedline currents  
  - _Common Mode_
    - _Origin_ Arises as part of the intended current distribution  
    - _Response_ Not suppressed; incorporated into system operation  
    - _Effect_ Feedline current contributes directly to radiation
    - _Vertical Coax Shield_ Functions as a radiator with maximum current at the apex and with reduced reliance on ground

- _Performance_ Produces a hybrid radiation pattern with horizontal and vertical components  

- _Mismatch Behaviour_
  - _Effect_ System currents adjust according to full antenna and feedline geometry  
  - _Consequence_ Current distribution and radiation depend on installation  

- _Loss & Heating_
  - _Loss_ Occurs in transformer and system under mismatch  
  - _Heating_ Transformer heating driven by current and mismatch  

- _Limitations_
  - _Dependency_ Strong dependence on feedline routing and geometry  
  - _Control_ Requires deliberate management of feedline section  

- _Interaction_
  - _System Effect_ Antenna and feedline form a single radiating system  
  - _Control Method_ A 1:1 choke defines the extent of the radiating feedline section  

- _Failure Mode_ Loss driven by mismatch and system current distribution, producing heating  

- _Comparison_ Distinct from OCF and NCW by intentional and direct integration of feedline radiation  

---

# Summary

- 4:1 Baluns
  - Connect a balanced load to an unbalanced source (e.g. coax to a balanced antenna)
  - Provide impedance transformation between source and load
  - Load imbalance or impedance mismatch drives unequal currents
  - In current baluns, imbalance current is forced into the transformer, increasing loss and heating
  - In voltage baluns, imbalance current is passed into the system, producing common-mode current on the feedline

- 4:1 UnUn - Autotransformer
  - Connects an unbalanced source to an unbalanced load
  - Provides impedance transformation without enforcing current balance
  - Load mismatch increases current and transformer loss
  - Common-mode current is not suppressed and becomes part of the antenna system
  - Feedline shield current is directly coupled to the antenna

- OCF Antenna
  - Uses a 4:1 current balun
    - Off-centre feed produces unequal currents in the antenna arms
    - Imbalance current is forced into the balun, producing loss (heating)
    - Common-mode current may appear on the feedline if choking is insufficient

- NCW Antenna
  - Uses a voltage balun, a radiating coax section, and a 1:1 choke
    - Equal voltages applied to unequal impedances produce unequal currents
    - Common-mode current flows onto the feedline and forms part of the radiating system
    - A downstream choke defines the effective radiating section of the feedline
    - Radiation behaviour depends on installation and feedline geometry
  - Construction and connection open to interpretation & variation

- NKO Antenna
  - Uses an UnUn, a defined radiating coax section, and a 1:1 choke
    - UnUn connects coax shield to the short antenna arm, producing in-phase current
    - Feedline shield current and short arm current combine as part of the radiating system
    - Common-mode current is an intentional component of operation, not a parasitic effect
    - Feedline section is defined and controlled as part of the antenna system
  - Construction and connections are explicitly specified to control current distribution

