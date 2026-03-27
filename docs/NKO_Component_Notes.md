# Antenna and Component Notes

---

## 4:1 Current Balun

- _Definition_ 
  - _4:1_ Indicates an impedance transformation ratio between input and output ports  
  - _Type_ A current balun (Guanella) is a transmission-line transformer that presents high impedance to common-mode current while enforcing equal and opposite currents at its balanced output terminals  
  - _Purpose_ Connects an unbalanced source to a balanced load while maintaining current symmetry    
- _Function_ Transforms impedance while attempting to maintain current balance  
- _Topology_ Transmission line or bifilar windings on ferrite cores (toroids)
- _Balance_ Forces current symmetry between antenna legs  
- _Choking_ Provides inherent common-mode choking   
- _Use Case_ Common in OCF antennas  
- _Performance_ Best with near-balanced loads  
- _Mismatch Behaviour_ Drives common-mode currents into ferrite impedance  
- _Mismatch Loss_ Increased core loss under mismatch conditions  
- _Mismatch Heating_ Ferrite dissipates imbalance energy as heat  
- _Common Mode Current_
  - _Origin_ Arises from load imbalance or impedance mismatch between the two output terminals
  - _Mechanism_ Forces equal currents regardless of unequal load impedances
  - _Suppresses_ feedline current via choking impedance
  - _Result_ The imbalance current is forced into the ferrite (choking path) rather than the feedline
- _Limitation_ Poor match for highly asymmetric systems  
- _Limitation_ Frequency-dependent choking effectiveness  
- _Loss_ Core loss increases with imbalance and impedance mismatch  
- _Heating_ Dissipates unwanted energy as heat  
- _Bandwidth_ Dependent on ferrite mix and winding  
- _Failure Mode_ Loss is driven by load imbalance and impedance mismatch, producing ferrite heating
- _In NKO Context_ Opposes intended behaviour

---

## 4:1 Voltage Balun

- _Definition_ 
  - _4:1_ Indicates an impedance transformation ratio between input and output ports  
  - _Type_ A voltage balun (Ruthroff) is an autotransformer that enforces equal voltages at its output terminals  
  - _Purpose_ Connects an unbalanced source to a balanced load without enforcing current symmetry   
- _Key Property_ Enforces voltage symmetry rather than current symmetry
- _Function_ Transforms impedance without enforcing current balance  
- _Topology_ Autotransformer-style winding  
- _Balance_ Does not correct current imbalance   
- _Feedline Behaviour_ Feedline may radiate  
- _Use Case_ Windom and Carolina Windom antennas  ("NCW")
- _Use Case_ Systems tolerating feedline radiation  
- _Performance_ Handles unbalanced loads  
- _Mismatch Behaviour_ Allows imbalance to pass into system  
- _Mismatch Loss_ Core loss increases with mismatch while additional current flows into the feedline
- _Mismatch Heating_ Heating occurs under high current imbalance  
- _Limitation_ No suppression of unwanted feedline current
- _Common Mode Current_
  - _Origin_ Arises inherently from the voltage-fed structure and lack of enforced current balance
  - _Mechanism_ Equal voltages are applied to unequal impedances, producing unequal currents
  - _Mechanism_ The difference current flows onto the feedline as common-mode current
  - _Result_ The feedline becomes part of the return path and radiating system
  - _Outcome_ Common-mode current is allowed to propagate rather than being suppressed
- _Loss_ Depends on mismatch and current  
- _Heating_ Can heat under imbalance  
- _Bandwidth_ Generally wideband  
- _Control_ Limited control of current distribution  
- _Interaction_ Often needs external choke  
- _Failure Mode_ Loss is driven by impedance mismatch and circulating current, producing ferrite heating
- _In NCW Context_ Used with downstream choke  
- _In NKO Context_ Does not provide the same phase relationship or current drive to the feedline

---

## 4:1 UnUn (Autotransformer)

- _Definition_ 
  - _4:1_ Indicates an impedance transformation ratio between input and output ports  
  - _Type_ An unun is an unbalanced-to-unbalanced autotransformer using a single winding with taps  
  - _Purpose_ Transforms impedance between unbalanced circuits without attempting to enforce current balance or isolate common-mode currents   
- _Key Property_ Does not attempt to separate antenna and feedline currents
- _Function_ Transforms impedance without balancing currents  
- _Topology_ Single winding with taps  
- _Connections_ High, low (common), and tap  
- _Balance_ Does not enforce symmetry  
- _Common Mode Current_
  - _Allows_ common-mode current without suppression
- _Feedline Role_ Feedline can radiate  
- _Use Case_ End-fed and asymmetric antennas  
- _Use Case_ NKO antenna systems  
- _Performance_ Handles asymmetric loads well
- _Mismatch Behaviour_ Passes imbalance directly into system currents 
- _Mismatch Loss_ Core loss depends on current and mismatch, with additional current flowing into the antenna system
- _Mismatch Heating_ Heating occurs from total current rather than suppression  
- _Advantage_ Simple construction  
- _Advantage_ Enables system-level current shaping  
- _Limitation_ No inherent choking  
- _Loss_ Depends on current and impedance ratio  
- _Heating_ Possible under load  
- _Bandwidth_ Depends on core and winding  
- _Interaction_ Part of total radiator system, in NKO antenna it demands an external 1:1 balun (choke) 
- _Failure Mode_ Loss is driven mainly by impedance mismatch and load current, producing heating
- _In NKO Context_ Promotes strong coax shield current drive, enables in-phase current addition  

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
  - _Structure_ Consists of two unequal-length conductors forming a balanced radiating element  
  - _Purpose_ Provides multi-band operation by presenting usable feedpoint impedances at harmonic frequencies  
- _Build_ Constructed with two unequal length arms, commonly around a 1/3 to 2/3 ratio
- _Feedpoint_ Located at an impedance point typically higher than 50 ohms
- _Transformer_ Uses a 4:1 current balun to transform impedance closer to 50 ohms
- _Current Balance_ Currents in each arm are generally unequal due to off-centre feed
- _Radiation Pattern_ Exhibits multi-lobed patterns that vary significantly with frequency
- _Harmonic Operation_ Often used across multiple bands via harmonic resonance
- _Feedline Behaviour_ Ideally low common-mode current when properly choked
- _Common Mode_ Imbalance can lead to feedline radiation if choking is insufficient
- _Loss Mechanisms_ Can include balun losses and coax losses under high SWR conditions
- _Perception_ Often described as a compromise antenna due to pattern and impedance variability

---

## New Carolina Windom Antenna

- _Definition_ 
  - _Type_ The New Carolina Windom (NCW) is a variant of the off-centre-fed dipole incorporating a feedline as part of the radiating system  
  - _Structure_ Consists of an off-centre-fed wire element with a coaxial feedline that carries common-mode current  
  - _Purpose_ Introduces a vertical radiation component by allowing controlled feedline radiation  
- _Feed Method_ Typically uses a voltage balun rather than a current balun at the feedpoint
- _Feedline Role_ The coax feedline is allowed to radiate as part of the antenna system
- _Choke Placement_ A 1:1 choke is placed some distance down the coax feedline to control current distribution
- _Radiation Structure_ Functions as a combination of horizontal wire and vertical radiator via feedline
- _Pattern Effect_ Introduces a vertical component to radiation, improving lower angle radiation
- _Control Aspect_ Feedline radiation is semi-controlled via choke placement rather than fully suppressed
- _Comparison to OCF_ Differs by intentionally using feedline radiation rather than treating it as a fault
- _Limitations_ Feedline behaviour can vary with installation and environment

---

## New Kallista OCF (NKO) Antenna

- _Definition_ 
  - _Type_ The New Kallista OCF (NKO) is a hybrid wire antenna system in which the feedline is an intentional radiating conductor  
  - _Structure_ Consists of an off-centre-fed wire element and a coaxial feedline forming a coupled three-conductor radiating system  
  - _Purpose_ Utilises controlled feedline current to shape radiation characteristics and current distribution  
- _System Nature_ The antenna and feedline form a single coupled radiating system
- _Design Difference_ Traditional antenna systems attempt to isolate the feedline from radiation; NKO intentionally integrates it
- _Core Principle_ The feedline is an intentional radiating conductor electrically coupled to the antenna, not a parasitic effect
- _Structure_ Comprises a long arm, a short arm, and the coax feedline forming a three-conductor system
- _Feed System_ Uses a 4:1 autotransformer (UnUn), not a traditional current balun or a voltage balun
- _Connections_ Long arm connects to the high side of the autotransformer
- _Connections_ Short arm connects to the common (low side) of the autotransformer
- _Connections_ Coax shield is bonded to the short arm at the feedpoint
- _Current Behaviour_ The short arm current and feedline shield current are in-phase and additive
- _Current Relationship_ Feedline shield current and short arm current are in-phase and combine as part of the radiating system
- _Balance Concept_ Improved balance compared to OCF and NCW is achieved between long arm and (short arm + feedline)
- _Feedline Role_ Feedline is a designed radiator, not a parasitic or fault condition
- _Radiation Pattern_ Produces a hybrid pattern with both horizontal and vertical components
- _Installation Sensitivity_ Feedline routing, especially the initial section, materially affects performance
- _Common Mode_ Common-mode current on the feedline is part of normal operation and contributes to radiation
- _Common Mode Interpretation_ Common-mode current is a functional component of radiation in this system, not inherently a loss mechanism
- _Comparison to OCF_ Unlike OCF, does not attempt to suppress feedline radiation
- _Comparison to NCW_ Provides more direct coupling of feedline current into the radiating system
- _Observed Behaviour_ Reports of improved intelligibility compared to EFHW and loop antennas
- _Observed Behaviour_ Enhanced higher-frequency audio components (e.g. fricatives)
- _Observed Behaviour_ Reduced perceived multipath distortion effects
- _Reciprocity_ Improvements observed in both transmit and receive scenarios
- _Classification_ Not a conventional dipole; better described as a controlled hybrid radiator
- _Not Equivalent To_ Standard OCF, EFHW, or uncontrolled feedline radiation systems


