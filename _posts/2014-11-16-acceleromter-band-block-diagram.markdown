---
layout: post
title:  "Accelerometer band block diagram"
date:   2014-11-16
categories: accelerometer
---
## Design requirements

Primary design goal of this product was power efficiency. Every single component was carefully picked to have as low
current requirement as possible. Good support for sleep mode was a must have. 

Feature set was a second major consideration.
Except of accelerometer we plan to add barometric pressure sensor to track altitude in outdoor activities but also
absolute depth in underwater. 1200mbar should be enough to be able to position tracking band underwater up to around 
 1.8 meters [[1]][1].

Important part of our device is storage capability allowing to register as many as 12h of data in rating 100Hz 
sampling and maximum resolution of sensors. 
To provide sufficient storage we pick flash based memory that can store up to 32Mb of raw data. 
In addition to that we've added FRAM chip [[2]][2] which is very fast nonvolatile memory and does not have 
limit of repeated writes, thus will ideally suit as a counter storage or buffer memory. Sensor data can be stored into 
FRAM memory to be processed in chunks and than move to flash for permanent storage.  

We plan to provide live communication with other Icarus devices or smartphones through Bluetooth Low Energy compatible radio,
which can be enabled as software device in nRF51822 processor [[3]][3]. That processor itself suits ideally to our needs as it
is extremely low power (150 μA/MHz running from RAM) and yet powerful enough. Besides embedded radio, key features are
RTC that can provide exact time even in sleep mode, 3PWM outputs that can be configured on any pins and 8 channels 
of 10bit DAC. We don't plan to use all of them but at least one will be used to monitor the battery voltage level.
  
BLE is great to provide live communication up to the speed of 4Kbps [[4]][4] which is enough to provide any type of 
information externally. Unfortunately it is not enough to enable download of stored information from raw sensors. 
Every hour of raw sensor measurement will require almost 1h30min downloading time. 
To make it better we plan to use UART on the processor and UART-USB converter as an external component to connect 
computer and Icarus Accelerometer Band for downloading. This will allow to have transfer speed at 1 Mbps which 
is far better than using BLE radio. The same amount of data can be download in just 20s theoretically.  


## Block diagram
![Accelerometer band block diagram][diagram]

## Processor

## Memory management
 
## Sensors

## Power consumption 

[1]: http://www.calctool.org/CALC/other/games/depth_press
[2]: http://en.wikipedia.org/wiki/Ferroelectric_RAM
[3]: https://www.nordicsemi.com/eng/Products/Bluetooth-Smart-Bluetooth-low-energy/nRF51822
[4]: https://bluegiga.zendesk.com/entries/22400867--HOW-TO-Maximize-throughput-with-BLE-modules

[diagram]: /img/posts/accelerometer/accelerometer-band-block.png  "Accelerometer band block diagram"
