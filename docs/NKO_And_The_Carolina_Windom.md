# Distinguishing the NKO from the (New) Carolina Windom

I get it. The NKO looks like a New Carolina Windom. There is a 4:1 at the feed point and a 1:1 current balun somewhere down the coax. The coax is intended to radiate, so the superficial conclusion is that they are the same antenna.

They are not.

## The differences are significant

**The 4:1 in the NKO is an UnUn**, and that is not a small detail. It is _not_ a balun. This distinction is central to the system's behaviour. In the NKO, the coax shield is directly bonded to the OCF short arm. That means feedline common-mode current is introduced deliberately by the connection topology, not merely as a by-product of a balun feeding an off-centre wire antenna.

**The length of the vertical coax has been refined**, and it differs from the New Carolina Windom for good reasons. The lengths we recommend were chosen because NEC modelling and field testing indicate better SWR behaviour and better radiation patterns for the design goals of the NKO.

**We specify a good 1:1 current balun at the bottom of the coax**, and this is not optional as it defines the coax above it as a vertical radiator and prevents common mode currint going past it to the shack. It is a boundary device. Some people call it a "line isolator", but I prefer "1:1 current balun" because that is what it is. The NKO deliberately places substantial current on the coax shield, so the 1:1 current balun has to be good enough to define the radiating section properly and keep the rest of the feedline out of the antenna system.

**The NKO has been analysed openly using NEC modelling, test builds, and modern tools.** There is substantially more technical detail available for the NKO than was ever published for the original Carolina Windom.

**NKO is _not_ a commercial product.** From what we can determine, the original Carolina Windom was sold commercially and its exact design was not published in full. NKO is openly documented and can be built by anyone.

---

## Where they are fundamentally similar (full disclosure)

- Both are based on OCF wire antennas
- Both intentionally radiate from the coax shield
- Both use a downstream 1:1 choke to define the boundary of the radiating feedline section
- Both are, physically and electrically, hybrid antennas with a horizontal wire section and a vertical feedline radiator
- Someone looking at both on a mast would struggle to tell them apart

The NKO may reasonably be described as:
- A principled redesign of the NCW concept
- The same broad idea, but with the coupling mechanism made more deliberate
- Feedline lengths explicitly optimised
- A system that is properly specified and documented

So yes, they are in the same family. No, that does not make them the same antenna.

---

## NKO performance

Test users have reported that the NKO works very well and that SWR is not degraded beyond what you would normally expect from an OCF antenna.

SWR and antenna performance are not tightly linked, but it is still useful when both are acceptable.

The more important point is the on-air behaviour. One test station reported that you "hear more stations and louder", which is consistent with the design doing what the analysis suggests it should do. Another report was that it sounded "more punchy" than a comparison antenna.

Our view is that the performance improvements of the NKO likely arise from several factors:
- The coax shield is driven strongly because it is directly bonded through the UnUn/short-arm arrangement, rather than relying on feedline current arising only as a secondary consequence of a balun feeding an off-centre load
- The UnUn may have lower loss than a comparable balun in this application because it is performing impedance transformation rather than simultaneously trying to enforce balance on an inherently asymmetric antenna system
- The phase relationships between the OCF arms and the vertical coax can produce a more favourable far-field pattern
- For an 80 m OCF, the 4.7 m vertical coax length gives a notably better 20 m far-field pattern in our NEC models

---

## About the New Carolina Windom

As far as I can tell, the New Carolina Windom most often uses a _4:1 voltage balun_ at the feed point. This connects the centre conductor of the coax to one side of the OCF feed arrangement, with common-mode current on the shield arising from the imbalance between the currents on the two OCF arms. There are several consequences to this:

**The 4:1 voltage balun can be connected in two ways** to the OCF arms, and I believe the choice can matter in practice because of the current relationships and the phase interaction with the vertical radiating coax.

**Common-mode current is part of the balun-driven system behaviour.** In that arrangement, the balun is involved in producing the current imbalance that then excites shield current. My view is that this is less direct, and potentially less efficient, than deliberately bonding the shield to the short arm and defining the radiating section with a proper 1:1 current balun lower down the feedline.

**Current phase on the coax shield is less explicitly controlled.** It may be in-phase, partly out of phase, or anti-phase with respect to current on the OCF arms. That matters, because the vector sum of those currents determines whether the vertical section reinforces or degrades the far-field pattern.

**The commonly cited vertical coax lengths are 22 feet and 10 feet.** These appear to follow a simple quarter-of-the-fundamental-in-metres expressed in feet rule. Antenna modelling for 22 feet on an 80 m antenna shows that the 20 m pattern is not as good as with a 4.7 m coax length in the NKO models. It may be somewhat better on 40 m, but 20 m is the prime DX band we are optimising for. The 10 ft length on a 40 m OCF is, notably, quite close to the 3.5 m NKO length. For NKO, we recommend these lengths on the basis of NEC modelling, user feedback, and field testing.

