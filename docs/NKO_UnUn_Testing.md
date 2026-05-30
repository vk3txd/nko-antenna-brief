# Efficiency Testing 4:1 UnUns (at HF)

When you build an UnUn, testing SWR is easy enough using a resistor. But SWR does not tell you how much power can you safely feed into it before it gets too hot from loss. We know the wire size, we know the core size, we can estimate power handling - but we really don't actually know what its power handling is.

Testing efficiency is therefore called for. That will give us a guideline as to how much power can be used before the UnUn or balun may be stressed to failure.

## Why Efficiency Matters

You will never ever notice the difference in signal strength between an efficient and an inefficient UnUn or balun. 

That has been used as a justification for not being concerned about efficiency.

However and very importantly, if your UnUn or Balun is highly efficient, there will be less loss and hence less heating of the core and that means a smaller core can be used at higher power. It also means digital modes that have a higher duty cycle meaning more average power and heating, can be more safely used than with an inefficient core.

An example. From testing we know that a QRP build using a 25mm diameter core can easily handle a 50W constant carrier key down power for 5 minutes because it is highly efficient. Testing shows the optimum build also (I tried 2 versions).

## Failure Mechanisms

Why do UnUns (and baluns) fail? There are 2 main mechanisms;

- Heat. Loss in the device translates into heat. If the core gets much past 120c (for the types of ferrite I've been using), the magnetic properties will change and loss will escalate. When this happens the core may shatter.
  - Don't forget ambient temperature. In VK on a hot summer day, the UnUn may be at 60c in the noon day sun even before you put any power into it.
  - Higher power means more heat. Longer transmit means more heat.
  - Microphone setting and compression affects heat (SSB).
  - The mode of operation matters. SSB has a low duty cycle, FT8 is higher and some digital modes are higher again. The higher the duty cycle the greater the heating.
- Voltage flashover. If the wire used in manufacture does not have good enough insulation, and it is damaged in the build, it may short out and cause damage, possibly to the transceiver.
  - The windings in the 4:1 UnUn have the full differential voltage across them.
  - If the SWR is high it may also elevate the voltage. 
  - I like teflon sleeving the winding wires for better insulation. Enamel covered wire just might be ok without sleeving - why risk it.

## Methods 

There are a few ways to test your 4:1 UnUn's efficiency. SWR is easy - just put a 200R resistor across the output and measure it with a VNA or SWR meter of some kind.

Efficiency is a little more difficult.

**1. VNA Testing** can be done in 2 ways; 

- by making 2 UnUn's, connecting them back to back and measuring through loss and dividing by 2.
- using just one 4:1 UnUn, connect the VNA Port-2 to the 200R side via a 150R resistor and adjust for loss in the resistor.

In my experience this does work, however the loss in a well made 4:1 UnUn is quite low. The VNA needs to be carefully calibrated and everything done carefully. The back to back method is the easiest.

Cutting to the chase, I did this and found the results inconclusive. I was sure efficiency was excellent, but I was also sure there was significant error in my method.

**2. Dummy Load Testing**

Build a 200R dummy load, connect the 4:1 UnUn to it and feed in power to the 50R side of the UnUn for a set time, set power, and then measure the temperature rise over time.

This is mildly painful as you need a temperature sensor bonded to the core, be able to read it, and of course have a dummy load capable of handling enough power over time.

Cutting to the chase, I did this on a number of builds (below) and got the kinds of numbers that agreed with VNA testing and resistor termination method.

**3. In-Situ testing with an antenna**

Probably the "gold standard" for testing. You are testing the 4:1 UnUn as you will be using it and getting a _real life_ result. The only variable is if you move the antenna and does that affect its performance.

The method would be to measure the temperature of the core(s) before the test, then apply power for a time then measure the temperature after the test, then using the temperature rise calculate efficiency.

Of course the antenna must be lofted after measuring the core temperature, the test power used, then pull the antenna down after the test and measure temperature to get the temperature rise.

Cutting to the chase, this is a 'gunna do' thing. I have not got-round-to-it yet.


# Dummy Load Testing

On 23 May 2026 I used a 600W 200 ohm dummy load to test a number of 4:1 UnUn builds. Below is the picure of the dummy load connected to the QRP UnUn (uses the LO1234 core). You can see it uses 4 x 50R resistors in series to make the 200R load. These must be insulated from the heatsink of course, and thermally bonded.

<img src="./dummy_load_4-1_UnUn.png" alt="Dummy load with UnUn connected" width="500">

I used an IC7410 transceiver set to 50W output as measured by a power meter, tuned at 7.1mHz, then fed that into the 4:1 UnUn connected to the 200 ohm dummy load. The SWR was 1:1 at 7mHz.

Side notes, 

- efficiency is calculated by finding the temperature rise of the ferrite core(s) after applying power. We know the weight of the core(s), the duration and amount of power. From that we know amount of power lost because of heating, and hence can calculate efficiency.
- I used an LM335 temp sensor. This is in a TO92 plastic package and taped to the core under test.
- the resistor rating of the dummy load is 600W, with a 50W signal for 5 minutes, the heatsink got nearly too hot to touch even though the heatsink is quite large. A fan was used after the first test, blowing down on the resistor packages.
- 50W key down constant carrier roughly relates to perhaps 250W of SSB - assuming an average power of 20% of peak.
- I used a comparatively high power because I wanted to _clearly_ see the temperature response. Measuring small temperature rises under lower powers is fraught with error. Even so, a 2c temp rise is still quite small.
- some of the wire used to make the UnUns is quite thin at 0.6mm, pushing that past 100W is not advised (and 100W may be ill advised).
- shown in the pic below is what I considered and termed a "QRP" UnUn prior to testing. This has a single 25mm core. With a 50W carrier fed into it for 5 minutes, it performed better than I thought it would, I expected it to get far hotter. My fear for this build is the small ferrite mass and hence heating under adverse conditions. Yes it is highly efficient, but that must be balanced by heating under loss.


| Build              | diam Weight | Power | Time | Temp Rise | Efficiency |
|--------------------|-------------|-------|------|-----------|------------|
| 1 x LO1234-6 turns | 25mm 15g    | 50w   | 300s | 18.4c     | 98.5% |
| 1 x LO1234-7 turns | 25mm 15g    | 50w   | 300s | 8.1c      | 99.4% |
| 2 x LO1234-7 turns | 25mm 30g    | 50w   | 300s | 3.8c      | 99.4% |
| 1 x LO1238-6 turns | 35mm 38g    | 50w   | 307s | 7.0c      | 98.6% |
| 1 x LO1238-7 turns | 35mm 38g    | 50w   | 305w | 4.4c      | 99.2% |
| 2 x LO1238-7-turns | 35mm 76g    | 50w   | 306s | 2.2c      | 99.2% |

**Interpreting The Results**

It is not a perfect test as it isn't connected to an antenna, but it is possibly indicative of what to expect, and excellent to compare builds.

These results are for a perfect load on the bench. A real antenna will be a different load which will affect performance. Tests at other dummy load impedances may show this.

Error will creep in from heat loss;
- Core cooling to free air during the test
- Heating the wire and supporting mount
- Heat in the wires leaked to the metal SO239

NKO will not have a perfectly balanced load like a dummy load, and it will have a reactive component. Load imbalance will incur extra core loss and it is highly likely that real life antenna use will present significantly different efficiency figures.

I would expect the NKO 4:1 to have different efficiency by band also. Each band will present a different load, with the vertical coax length having a different impact on the currents and hence efficiencies.

The LO1234 core is quite small (25mm diameter) yet it handled 50W key down for 5 minutes like a champion when used with a 7 turn build. Trying a build with 6 turns resulted in over double the heating and loss.

A side note. AI did an analysis of this core and recommended 6 turns. I tried 7 turns "just to see what happens" and clearly it has lower loss. Trying 8 turns sounds sensible, the fact is with teflon sleeved wire, there is not enough space on the inside of the core to actually fit more turns without stacking them.

The LO1238 core is still small at 35mm diameter. With 6 turns it performed very similarly in efficiency to the half sized LO1234 (25mm) core with 6 turns.

Putting 7 turns on the LO1238 showed the same efficiency as a 2 core version and double the temperature rise - so they line up rather well.

The dual LO1238 and 7 turns, using 1mm ECW teflon sleeved wire, turned in a result that indicates it should work well at 400W SSB and with ease.

Looking at the efficiency results, it is clear that the number of turns is the efficiency driving factor.

Lead dress matters. Keep the 50R side leads short and neat. The 200R side of a 4:1 is not so critical, but keeping it neat also helps. You'll see the effect when you run an SWR test using a 200R resistor. Long leads will make the SWR climb particularly at the top end of HF.


## Tests At Other SWRs

How a device performs when operated into a non-optimum load is important. An antenna is almost guaranteed to not result in a perfect 1:1 SWR - so the simple question is "how efficient is it with a poor SWR?" The last thing we want is for the UnUn to be destroyed on a poor antenna and/or damage a transceiver.

For test this I changed my dummy load to have a different resistance, hence SWR, and reduced the power I fed in - just in case efficiency suffered badly. Temp rise of the core indicates efficiency.

| Build              | diam Weight | Power | Res  |  SWR  | Time | Temp Rise | Efficiency |
|--------------------|-------------|-------|------|-------|------|-----------|------------|
| 2 x LO1234-7 turns | 25mm 30g    | 20w   | 100R |  2:1  | 300s |   2.3c    | 99.1% |


**Interpreting the results**

Again, the only thing that can be said; "On the bench into a balanced and non reactive 100R dummy load the UnUn showed the given efficiencies" - extrapolating this to performance with a real antenna cannot be assumed. 

A 2:1 SWR and 100R resistance will increase the current in the windings. This did not seem to be a concern. For the LO1234 build, I used 0.63mm wire sleeved in teflon tube.

However, the UnUn still performed very well.


## Thermal Headroom

I used AI to crunch the numbers for efficiency. I asked it what the performance indicated. It used a term "Thermal Headroom".

It defined Thermal Headroom as "Thermal headroom means how much extra heat a part or system can tolerate before it reaches an unsafe, unreliable, or performance-changing temperature."

Example: If a core starts at 25°C and reaches 35°C in a 50 W test, it has far more thermal headroom than a core that reaches 80°C in the same test. Of great importance, remember, ambient temperature matters. If the UnUn/Balun is in the sun and _already_ hot, adding a lot more heat can push it past safe levels.

From the tests, the more efficient an UnUn is, the less heating, and the heavier the core is the more heat it can absorb before heating badly. So if you have high efficiency and heavier cores, the thermal headroom is the greatest.

On a practical note, if the core is small and light and operated into a very poor load, the efficiency will suffer and being lighter will heat more than a heavier core might do.

Finally, the cores dissipate heat into its environment. Inside a box with poor air flow. Generally my expectation is that a core may rise in temperature faster than it cools. At the same time, 2 cores stacked will have a larger surface area which may cool faster.


## Derating Advice

I have not tested these for efficiency with a real antenna which will most likely increase the loss. The following are conservative suggestions.

I suggest the following;
- LO1234 core 7 turns, derate to 25w SSB max
  - the core is small with a low thermal mass. Operating it into non-ideal loads may heat more.
- LO1234 x 2 cores, 7 turns, derate to 50w SSB max
- 1 x LO1238 core 7 turns, derate to 100w SSB max
- 2 x LO1238 cores 7 turns, derate to 400w SSB max
  - built with 1mm wire

All builds _should_ handle those kinds of powers very well. into a well matched antenna, close to 1:1 it is likely they will handle far more power. if you do put more power in, monitor SWR closely.