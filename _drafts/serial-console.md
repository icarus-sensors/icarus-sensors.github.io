---
layout: post
title:  "Starting with nRF51822"
date:   2014-11-18
categories: general
---
###USB Serial Console

The last part that you may find very handy while working with embedded is some sort of USB to UART converter. They are also
called USB Serial Console cable. There is no point to go through all of possibilities here right now but to just let you know,
we will be using one that is based on CP2102 chip from Silicon Labs [[8]][8]. You can find plenty of them on eBay. 

![Mini CP2102 USB 2.0 to UART][Mini CP2102]

If you have this one or other which is based on CP210x download and install 
[CP210x USB to UART Bridge VCP Drivers](http://www.silabs.com/products/mcu/pages/usbtouartbridgevcpdrivers.aspx).


To communicate through serial console we will be using just screen. It is not maybe the most convenient way but for our needs
 it is just enough. There are plenty of other possibilities that you can find in internet, pick one that you like the most [[12]][12].
