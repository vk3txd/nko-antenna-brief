# Efficiency Testing 4:1 UnUns (at HF)





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

On 23 May 2026 I used a theoretical 600W 200 ohm dummy load to test a number of 4:1 UnUn builds. Below is the picure of the dummy load connected to the QRP UnUn.

<img src="./dummy_load_4-1_UnUn.png" alt="Dummy load with UnUn connected" width="500">

I used an IC7410 transceiver set to 50W output as measured by a power meter, at 7.1mHz, then fed that into the 4:1 UnUn connected to the 200 ohm dummy load.

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

