# Field Testing 4:1 UnUns

Lab testing an UnUn is fairly straighforward and once "tooled up" quite a few can be tested in an hour or two.

- Putting a resistor on their output and using something to measure SWR you can see impedance transforming performance over frequency. At the top end of HF things can change depending on winding, cores, and pigtail lead dress.
- A VNA can be used to measure loss (and SWR) quite easily, though experience has shown me that highly efficient devices pose issues of accuracy and do require very careful calibration and use.
- Using a transmitter and high power dummy load, the temperature rise under power over time can be measured then efficiency calculated. There are a few sources of error - but it can be at least 'indicative.'

All these are excellent tests and worthwhile. But they don't test as how you are actually going to use the device(s) in the field.

This doc will detail field tests that are intended to test and measure how UnUns and Baluns as they are actually used with an antenna, "in-situ".


## Goals

The end goal is to determine;

- how much loss, and hence stress, a device in the field experiences with actual use with an antenna.
  - NKO 4:1 UnUn
  - NKO 1:1 balunn
  - OCF 4:1 current balun in a conventional OCF
- the current distribution the system.
  - NKO is a "3 conductor" system - the two OCF arms and the intentional coax shield. How much current does each carry?
  - Repeat for a conventional OCF that uses a 4:1 current balun
  - The goal being to compare an OCF to the NKO.

I've seen and done tests on common mode current back at the transceiver. It is actually very worthwhile and I recommend it so that you know what you are dealing with and if you have al atent problem. Never have I seen those kinds of tests done at the apex of an antenna. 


## Why am I pursuing this so much?  

It interests me. Pure and simple. I've not seen this done at anywhere near this depth elsewhere. Sure, there is plenty of supposition but no actual measurement so far as I know.

I have many questions;

- How does the UnUn change its efficiency when used with an antenna, with a reactive and off-perfect impedance load?
- How does it change by band?
- Does the NKO vertical coax truly carry significant current, by band, and how well balanced is the load presented to the UnUn?

A wise person said in his no longer available blog, and paraphrasing, "_until you measure, you don't really know._"


## Methods

There are 2 methods in mind;

- Simple temperature rise
  - measure the temperature of the core(s)
  - loft the antenna then energize for a measured power and known time.
  - drop the antenna and measure the temperature rise, then from that calculate efficiency.
  - this must be repeated for each band.
  - It tells us nothing about currents - and it painstaking to say the least. A great job for someone else.
- A better method 
  - I have a cunning plan - to be revealed when implemented.


History
31 May 2026 - initial write