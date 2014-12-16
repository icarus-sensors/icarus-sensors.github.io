---
layout: post
title:  "SPI Connection Considerations"
date:   2014-11-18
categories: general
---
## Connecting devices with SPI

We want to connect quite a few slave devices to nRF51822 to gather sensor data and also store them for post processing
and offline analyze. We've found that SPI line will be more appropriate for us as we have plenty of GPIO pins and two SPI
lines available for communication on CPU.  

SPI consist of four lines. 

CLK - line clock 
MOSI - master output slave input (SDI) 
MISO - master input slave output (SDO)
CS - chip select (separate for every slave chip)

Connecting multiple devises require having separate line for CS functionality for every slave devices we want to connect.

## Line protection


### Option 1 - Leave line unprotected

First option is somehow trivial but still worth mentioning. It may really be the case that any protection effort is 
unnecessary and all lines may be leave clear. It will save some space and simplify design a lot so this is right now 
our option 1. Hope that it will be possible.  

### Option 2 - Source termination

Second option involces adding serial resistor as close to any chip which is driving that lines as possible. If line is 
driven only by one other chip like in CLK case, when master can only change that line, there will be only one resistor, in any 
other situation every chip which can change line signal will get serial resistor.
 
Value of that resistor should be identical to the line impedance. What does it means exactly we have to figour out. For now
we just leave a place for it on our designs and when they will be manufactured will get back to that. 
 
For those of you who need some more details right now there is quite good explanation of stackexchange [[1]][1]. 
 
<quote>
 I said before that your series resistor for source termination must be located at the driver, and it must have the same value as your trace impedance. That was an oversimplification. There is one important detail to know about this. Most drivers have some resistance on it's output. That resistance is usually in the 10-30 ohm range. The sum of the output resistance and your resistor must equal your trace impedance. Let's say that your trace is 50 ohms, and your driver has 20 ohms. In this case your resistor would be 30 ohms since 30+20=50. If the datasheets do not say what the output impedance/resistance of the driver is then you can assume it to be 20 ohms-- then look at the signals on the PCB and see if it needs to be adjusted.
 
  
### Option 3 - R-C low pass filter

[1]: http://electronics.stackexchange.com/a/33380/58915
[2]: http://electronics.stackexchange.com/a/33375/58915


https://learn.sparkfun.com/tutorials/designing-pcbs-advanced-smd