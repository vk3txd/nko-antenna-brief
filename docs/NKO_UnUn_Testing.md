# Efficiency Testing 4:1 UnUns (at HF)

When you build an UnUn, testing SWR is easy enough using a resistor. But how much power can you safely feed into it. We know the wire size, we know the core size, we can estimate power handling - but we really don't actually know.

Testing efficiency is therefore called for. That will give us a guideline as to how much power can be used before the UnUn may be stressed to failure.

## Why Efficiency Matters

You will never ever notice the difference in signal strength between an efficient and an inefficient UnUn or balun. 

That has been used as a justification for not being concerned about efficiency.

However and importantly, if your UnUn or Balun is highly efficient, there will be less loss and hence less heating of the core and that means a smaller core can be used at higher power. It also means digital modes that have a higher duty cycle meaning more average power and heating, can be more safely used that with an inefficient core.

An example. A QRP build using a 25mm diameter core can handle a 50W constant carrier key down power for 5 minutes because it is highly efficient. 

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
  - I like teflon sleeving the winding wires for better insulation. Enamel covered with just might be ok - why risk it.

## Methods 

There are a few ways to test your 4:1 UnUn's efficiency. SWR is easy - just put a 200R resistor across the output and measure it with a VNA or SWR meter of some kind.

Efficiency is a little more difficult.

**VNA Testing** can be done in 2 ways; 

- by making 2 UnUn's, connecting them back to back and measuring through loss and dividing by 2.
- using just one 4:1 UnUn, connect the VNA Port-2 to the 200R side via a 150R resistor and adjust for loss in the resistor.

In my experience this does work, however the loss in a well made 4:1 UnUn is quite low. The VNA needs to be carefully calibrated and everything done carefully. The back to back method is the easiest.

Cutting to the chase, I did this and found the results inconclusive. I was sure efficiency was excellent, but I was also sure there was significant error in my method.

**Dummy Load Testing**

Build a 200R dummy load, connect the 4:1 UnUn to it and feed in power to the 50R side of the UnUn for a set time, set power, and then measure the temperature rise over time.

This is mildly painful as you need a temperature sensor bonded to the core, be able to read it, and of course have a dummy load capable of handling enough power over time.

Cutting to the chase, I did this on a number of builds (below) and got the kinds of numbers that agreed with VNA testing.

**In-Situ testing with an antenna**

Probably the "gold standard" for testing. You are testing the 4:1 UnUn as you will be using it and getting a _real life_ result.

The method would be to measure the temperature of the core(s) before the test, the apply power for a time then measure the temperature loss and calculate efficiency.

Of course the antenna must be lofted, thn pulled down after the test.

Cutting to the chase, this is a 'gunna do' thing. I have not got-round-to-it yet.


# Dummy Load Testing

On 23 May 2026 I used a theoretical 600W 200 ohm dummy load to test a number of 4:1 UnUn builds. Below is the picure of the dummy load connected to the QRP UnUn (uses the LO1234 core).

<img src="./dummy_load_4-1_UnUn.png" alt="Dummy load with UnUn connected" width="500">

I used an IC7410 transceiver set to 50W output as measured by a power meter, tuned it at 7.1mHz, then fed that into the 4:1 UnUn connected to the 200 ohm dummy load.

A side note, the resistor rating of the dummy load is 600W, with a 50W signal for 5 minutes, it got nearly too hot to touch even though the heatsink is quite large. A fan was required.

| Build              | diam Weight | Power | Time | Temp Rise | Efficiency |
|--------------------|-------------|-------|------|-----------|------------|
| 1 x LO1234-7 turns | 25mm 15g    | 50w   | 300s | 8.1c      | 99.4% |
| 1 x LO1234-6 turns | 25mm 15g    | 50w   | 300s | 18.4c     | 98.5% |
| 1 x LO1238-6 turns | 35mm 38g    | 50w   | 307s | 7.0c      | 98.6% |
| 2 x LO1238-7-turns | 35mm 76g    | 50w   | 306s | 2.2c      | 99.6% |

**Interpreting The Results**

These results are for a perfect load. A real antenna load will be different which may affect performance. Tests at other dummy load impedances may show this.

I would expect the NKO 4:1 to have different efficiency by band also. Each band will present a different load, and the vertical coax length will have a different impact on the currents and hence efficiency.

The LO1234 core is quite small (25mm diameter) yet it handled 50W key down for 5 minutes like a champion when used with a 7 turn primary. Changing back to 6 turns resulted in over double the heating and loss. Calling this a "QRP build" is doing it an injustice.

The LO1238 core is still small at 35mm diameter. With 6 turns it performed very similarly in efficiency to the half sized LO1234 (25mm) core.

Putting 7 turns on the LO1238 is an obvious future test - I didn't have one available. Looking at the results, my guess is that it will reduce loss.

The dual LO1238 and 7 turns, using 1mm ECW teflon sleeved wire, turned in a result that indicates it should work well at 400W SSB and with ease.

