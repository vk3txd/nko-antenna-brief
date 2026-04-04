# NKO Thinking Points

Here are some notes on the NKO that are at this stage, "thinking points" meaning unverified but worthy of discussion.

I've not used AI for the analysis or content, but used it for santity checking.

## Saturation and Component Failure

Some Amateur Radio and often AI has a habit of talking about saturation in amateur radio ferrite core'd components.

Please, before raising this as an option or a problem, compare the Bsat for ferrite versus the power required for saturation. It is a popular myth and easy target, like the booge man, to suggest this is a failure mechanism.

Saturation will not happen with Amateur Radio power levels in typical ferrite cores. The Bsat is extremely difficult to reach under these conditions. 

Failure of a Balun or UnUn is most likely to happen because of;
- Heating. Heating caused by loss, ferrite core properties, poorly designed winding ratios and geometries, imbalance currents
  - My own testing showed a 98% efficient 4:1 current balun at 200 ohms, was only 85% efficient at 135 ohms - my measuring temperature rise
- Voltage flashover. At very high power and under adverse SWR situations high voltages can be present
  - Using teflon sleeve over enamel covered wire is advised for the UnUn as high differential voltages will be present side-by-side
  - Using RG316 or better coax in the 1:1 makes a lot of sense for voltage withstand. 

For saturation to happen a _lot_ of power is required;
- Two examples - #43 material saturates at around 350mT
  - 100W into a single FT140-43 core with 8 turns bifilar might have approx 7mT - nowhere near sturation
  - 1000W into a single FT240-43 core with 8 turns bifilar might have approx 11mT - still nowhere near saturation

## Single Port Diversity Antenna - Or Hybrid Antenna

NKO has been described as thus.

Hybrid suggests multiple things combined in some fashion.

These terms are saying that the horizontal arms of the OCF and the vertical coax shield produce horizontal and vertical radiation patters. Since there is only one coax cennection (hence a single port) - it is gets that name.

Diversity suggests 2 antennas. For NKO which has a definite contribution of vertical radiation from the coax shield and of course the horizontal arms - this is why it has been described as a 'diversity' antenna.

Of the two terms, I prefer the used of 'Hybrid' as a diversity antenna system makes me think of 2 separate antennas.

## Current Balance

Connecting 2 antenna arms of different lengths to the UnUn presents differing impedances to the device. This will then imply different current flows for the terminals.

The NKO connects both the vertical coax shield and the short arm to the UnUn terminal. This _may_ improve the current balance as the short arm current could otherwise have been expected to be the lower current terminal. Adding current into the coax may improve balance.

_This all falls apart_ when we consider that the antenna may be used from 3.5mHz to 30mHz and hence the current on the coax shield and the arms may be completely different at some frequencies compared to this simplistic suggestion.

I have not seen any results from data logging currents at an OCF feedpoint. Yet.

## System Loss

First and foremost, the OCF antenna system uses 2 different length main radiating arms. They present different impedances to the matching device (UnUn or Balun) and hence different voltages and currents on its terminals.

_In NKO - The 4:1 UnUn_
- Only provides impedance transformation
- The suspected improvement in current balance may translate into lower system loss
- Common mode current that for baluns that may be used to heat the balun cores, for an UnUn is passed onto the coaxial cable radiating section and actually used.
- We surmise thie combination may result in the least system loss compared to all other OCF implementations.

_Compared to a conventional OCF and Baluns_
- A 4:1 current Balun
  - Uses the choking impedance of its components to reduce current on the coax 
  - When the SWR of its load (the antenna) is other than 200R, loss increases significantly
  - The Balun must deal with the imbalanced loads leading to heating and hence loss
- A Voltage Balun
  - Equally must deal with the imbalanced load
  - Common mode current is signficantly higher than for a current balun, but it is as a result of the 'magnetics' of the balun with different phase relationships to the antenna arms

The more I an UnUn is considered, the more I am convinced that while using a Balun in an OCF does work and can work very well, an UnUn will have lower loss.

_How much loss_ are we taling about and what is the signal improvement to be expected? If the loss was as _high_ as 1dB I would be slightly surprised. That may not translate into raw antenna 'gain' - and quite frankly, I think this loss only matters in terms of how the UnUn survives (heats up) under power.

## Current On The Coax Shield

The UnUn connects the shield of the coax to the short arm. It is driven directly, the same as the short arm.

By contrast the New Carolina Windom that tries to drive current onto the coax shield uses a voltage Balun. The amount of current is proportional to the imbalance of the current into the other 2 arms and depends on the magnetic properties of the Balun.

It is my contention that the UnUn provides more current to the coax shield, compared to a voltage balun.

## Signal Strength Improvements

To date testers of the NKO have said it 'hears more stations louder' and that is a direct quote.

The testers are using SSB in VK3 and VK5 - how this translates to other countries is open to discussion. By opening this repository it may bring more test stations - and their signal reports will be welcomed.

Looking at the 3-wire NEC models (in this repo) it is suggested that the gain improvements do not translate to reported performance. NEC shows minimal change in raw gain.

That then leaves only the change in pattern, take off angle, that explains the reported observations.

It is also possible that the phase relationships between the currents are aiding signal improvement.

## Feedpoint Phase Relationships

At the feedpoint, with an UnUn the shield of the coax is connected to the short OCF arm, so they are driven from a common source by the UnUn and at this point are in-phase. How that changes over HF remains unknown.

By contrast the New Carolina Windom drives the coax by the imbalance between the two OCF arms currents and has a phase difference compared to both other antenna arms. Again, how this translates to signal strength is unknown, but it is a more complex relationship that includes the voltage Balun.

My point is therefore that an UnUn may have a better phase relationship in the 3 conductors leading to signal improvements.

## Top Fed Vertical

The coax shield is fed, driven, at the apex of the antenna at the feed point high in the air. It can be (very roughly) considered as a vertical antenna upside down with the highest current point highest in the air.

This then places the point of maximum radiation at the highest point.

It also reduces the dependance, on the ground under the antenna. It may also lead to less loss.

## Stress On Components

There are 2 components to consider; the 4:1 UnUn, and the 1:1 current balun (choke).

_The 4:1 UnUn_
- This does not attempt to choke off or handle common mode current in any way
- It only performs impedance transformation
- The (suspected) improved current balance at its terminals may reduce stress on this component compared to any kind of balun.

_The 1:1 Current Balun (choke)_
- At the bottom of the coax, the 1:1 balun defines the vertical coax above it as a radiator
- There may be significant current on the shield of the coax that the 1:1 must handle
- On 80m, the current may be the highest in the system (for an 80m build) compared to 40m and 20m
- The 1:1 needs to be able to handle this current by having sufficient choking impedance and thermal mass
- It is surmised this will be the most stressed part of the antenna system