---
layout: post
title:  "Tuning an Electric Ducted Fan with an Arduino"
date:   2011-07-01 12:00:00 -0700
categories: jekyll update
---
# Motivation
For many years, hobbyists building electric remote-control planes could not build scale jets. Often to build a jet fighter, they unaesthetically had to put a motor and propeller in the front or rear of the aircraft.
However, thanks to the improved power outputs of lithium polymer batteries and the high RPMs of modern electric motors, electric ducted fans (EDF) have grown in popularity and in turn enabled hobbyists to design beautiful new electric remote-control planes that were previously unattainable.
To maximize the performance of an EDF, and thus the performance of the airplane, the fan blades of the EDF should be identical in mass and airfoil shape--discreancies in these parameters will result
in reduced RPMs and lower thrust. While airfoil shape is complex and hard to control post-manufacturing, it turns out that we can roughly tune the mass of the blades with some careful sanding
to improve the balance, reduce vibrations in the EDF assembly, and improve thrust.

# How it works
The system works by iteratively measuring vibrations in the EDF assembly and gently sanding the fan blades. Vibrations are measured using an [Arduino][arduino], an [accelerometer][sparkfun], and a PC running the Arduino IDE and a spreadsheet software (e.g. Excel).
First the EDF is attached securely to a thrust stand on a table. The EDF assembly includes a battery pack, speed control, and radio receiver, so that the throttle can be controlled from the transmitter.
Next, the accelerometer is securely attached to the EDF housing. Ideally it would be firmly glued on, but since that may make it harder to reinstall the EDF housing, I opted to very securely tape the accelerometer to the housing. Any extra movement in the accelerometer may throw off measurements.
With the accelerometer streaming data to the Arduino, and the Arduino sending serial data to the PC, the measurement begins and the EDF is throttled up to between ~75% (ideally the throttle level you'll be flying at for longest).
Data is then collected for ~20 seconds before throttling down, and the data can be imported into Excel from the Arduino serial monitor. Once in excel, you can calculate the standard deviation for that measurement position. 

# Still to do
<ol>
<li> Post photos of the test setup. </li>
<li> Check on the exact steps with dad and make the description more concise. (just describe what you did, not necessarilly all the details). </li>
<il> Post arduino/excel files if I still have them</il>
</ol>


[arduino]: https://arduino.com/
[sparkfun]: https://sparkfun.com/
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
