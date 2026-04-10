# Distinguising The NKO and (New) Carolina Windom

I get it. The NKO looks like a New Carolina Windom. We have a 4:1 at the feed point then a 1:1 Balun somewhere down the coax. The coax is meant to radiate, so the (wrong) conclusion is they are the same.

## The differences are significant

**The 4:1 Is an UnUn In NKO** and this is not a small difference. It is _not_ a Balun. This distinction is critical to the system's behaviour. The UnUn directly connects the shield of the coax to the OCF short arm. Current on the short arm is put there by a direct connection - and _not_ by the properties of a balun and the mismatch of the OPCF arms.

**The length of the vertical coax has been refined** and hence it is different to the New Carolina Windom. Choosing the lengths we have means the SWR of the antenna is better and the radiation patterns are better.

**We specify a good 1:1 current balun at the bottom of the coax** and this is not optional. Some people call it a "line isolator" but I prefer "1:1 current balun" as that is what it is. NKO puts more current on the coax shield than a 'Carolina and hence the 1:1 must be up to the task. You need a good 1:1 current balun.

**We have used AI and Modern Analysis** for the NKO and been very open in this, and we have a lot more information about it than was ever published on any 'Carolina.

**NKO Is _not_ A Commercial Product** from the information we can find, the original 'Carolina Windom' was a commercial product and it is actual design was not published as far as I can find. NKO is freely open to be built by anyone.

**Finally, ask AI to do a comparison** between the NKO and the New Carolina Windom. We have.

---

## Where they're fundamentally similar (full disclosure)

- Both are based on OCF wire antennas
- Both intentionally radiate from the coax shield
- Both use a downstream 1:1 choke to define the radiating section boundary
- The physical appearance and operating principle 
  — horizontal wire plus vertical feedline as a hybrid radiator are in the same family of antenna
- Someone looking at both on a mast would struggle to tell them apart

The NKO may be described as
- A principled redesign of the NCW concept 
- Same broad idea, but with the coupling mechanism replaced by something more deliberate
- The feedline length(s) optimised
- The system properly specified and documented

This is the difference between something that works for reasons that aren't fully understood, and something designed to work for reasons that are.

---

## NKO Performance

Test users universally report that NKO works very well and that the SWR is not degraded over what you would expect for an OCF.

SWR and antenna performance are not normally and closely related, but it is nice to have both.

The main thing however remains, and as a test station reported, you "hear more stations and louder" which indicates that the design is doing what the analysis shows it should do. Another report was that it sounded "more punchy" compared to another antenna.

We suggest that the performance improvements of NKO are because of the differences;
- The coax shield is driven very strongly by an UnUn because of the way it is directly connected, as compared to a Balun where the shield common mode current is a by-product of the Balun's performance
- We suggest the UnUn will have less loss than a Balun. It is only performing impedance transformation
- The phase relationships between the arms of the antenna and the vertical coax result in a better far-field pattern
- For an 80m OCF, the 4.7m vertical coax length results in an optimal far field pattern on 20m

---

## About the New Carolina Windom

As far as I can tell, the New Carolina Windom most often uses a _4:1 Voltage Balun_ at the feed point. This directly connects the centre of the coax to one of the OCF arms. Common mode current on the shield is proportional to the difference in currents on the OCF arms. There are a few consequeences to this;

**The 4:1 Voltage Balun can be connected in 2 ways** to the OCF arms, and I am sure it makes a difference. The reason is because of the current relationships and the phase interaction compared to the vertical radiating coax

**Common Mode Current** is as a result of balun performance, it is involved in producing that current and as a consquence of using a balun which is trying to force balance on an unbalanced antenna. I believe this is sub-optimal as it will cause loss and heating of the balun core

**Current Phase On the Coax Shield Is Indeterminate** meaning that it may be in-phase, out of phase or anti-phase with relation to the current in the OCF arms. Does this aid (reinforce) or reduce (cancel) in the vector-sum radiation pattern of the far field? I doubt it will be optimal as the impedance of the Balun windings will make it have a different phase to both antenna arms.

**The vertical coax lengths are 22 feet and 10 feet** and I have no idea where these came from. Antenna modelling for 22 feet (on an 80m antenna) shows the pattern on 20m is not as good as a 4.7m coax length. The models are in this repo - load them into 4NEC2 software to see for yourself. It may be a little better on 40m, but 20m is the prime DX band we are optimizing for. The 10ft length on a 40m OCF is very close to the 3.5m of NKO length. For NKO, we recommend these lengths based on NEC modeling and actual user feedback and testing.


