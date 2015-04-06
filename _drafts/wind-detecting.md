---
layout: post
title:  "Wind Detection with Barometric Pressure Sensor"
date:   2015-01-05
categories: general
---
## Explain idea

In 9DOF Shield we've included three external barometric pressure sensors. The idea behind having more than one sensor is 
one devices come from the need to measure static and dynamic pressure at the same time [[1]][1]. Sensor oriented in parallel to
 the wind direction will be measuring static pressure whereas one facing directly into wind source will be measuring 
 dynamic pressure on top of the static one. In that configuration we will be able to compute equations given in a Pitot
 Tube description [[2]][2] and compute wind speed. 
 
Two sensors would be enough to be able to make experiments with Pitot Tube but what we would also be able to do is to 
detect wind direction and that is why third sensor is necessary.  


[1]: https://www.dwyer-inst.com/Products/AirVelocityIntroduction.cfm
[2]: http://en.wikipedia.org/wiki/Pitot_tube


https://learn.sparkfun.com/tutorials/designing-pcbs-advanced-smd