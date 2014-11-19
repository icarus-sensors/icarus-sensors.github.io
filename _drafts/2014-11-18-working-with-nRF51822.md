---
layout: post
title:  "Working with nRF51822"
date:   2014-11-18
categories: general
---
##What is it all about

When we come across nRF51822 [[1]][1] processor we immediately new that this is something extremely interesting and will let us do
plenty of cool stuff with microdevices or so call wearables Do be honest we didn't even bother to check any other chip for 
similar functionality. It has everything that we need: Cortex M0 CPU, integrated 2.4GHz radio circuit,Real Time Clock, 
plenty of GPIOs, DAC and other stuff that you expect to find in other microcontrollers.

Hardware features alone might make you enthusiastic about this chip, but this is even more to come. Second the most important
factor for hobby projects and starters like we are is the convenient and easy to use software stack. It just so happens that
this processor is one of the many cover by ARM mbed [[2]][2] ecosystem which might be called "Arduino" in ARM world. It is
really easy to program those chips with minimal and affordable necessary tools. It is super cool and allows us to immediately 
jump to program those processors and learn to use it instead of just trying to figure out how it works and think if we can afford 
expensive developer board.

##Tools and Software

###nRF51822

First you need some development board of nRF51822 processor. There are plenty of different kits available and you have to pick your
own based on your needs and the price you want to pay. What we are using right now is sometimes called Core51822 [[3]][3]. Basically it is just
a minimal board with nRF51822 and on board antenna made in China. You can find it also on eBay for less than 10$, just search for nRF51822.

![Cheap development board for nRF51822][Core51822]

Of course, we would rather use some official development board like nRF51822 Development Kit [[4]][4] or nRF51 DK [[5]][5] 
which is the new version of the previous one, but we can't really afford to spend that much on it at the moment.

###Programmer

Switching from Arduino to ARM one problem to overcome is to find good programmer in affordable price. JTAG programmers can cost
far more than all your development boards. It will be obvious stopper for doing projects based on ARM. Hopefully we have found
ST-LINK/V2 [[6]][6], which is not that expensive. You can also by some compatible devices on ebay or build your own [[7]][7].

![ST-Link V2 mini programmer][ST-Link V2 mini]

###USB Serial Console

The Last part that you may find very handy while working with embedded is some sort of USB to UART converter. They are also
called USB Serial Console cable. There is no point to go through all of possibilities here right now but to just let you know,
we will be using one that is based on CP2102 chip from Silicon Labs [[8]][8]. You can find plenty of them on eBay. 

![Mini CP2102 USB 2.0 to UART][Mini CP2102]

###Breadboard, wires, diodes

To make life easier at the beginning it is good to have a breadboard, bunch of wires, few resistors and diodes. You 
can buy all of that in your local electronic shop or at eBay.
 
![Breadboard with some wires][Breadboard]

###Software stack

To program ARM we will need software to communicate with on chip debugger and gcc compiler for ARM. In this project we are 
using OpenOCD [[9]][9] and GNU Tools for ARM Embedded Processors [[10]][10]. It is also necessary to install SRecord [[11]][11], 
which is used for preparing binaries to be loaded into the microcontroller. All of the programs are opensource and available for linux and mac osx as well.

In the code example we will be using mac osx, but this should be almost the same for other unix system including linux. Just download proper packages and install it according to your distribution installation procedure. It will be good if you can put it in the
comments or drop us an email so we can extend this guide. 

####Macosx 

Step 1 - If you don't have already just install Homebrew first.  
[http://brew.sh/](http://brew.sh/)

Step 2 - Execute in terminal window:

{% highlight sh %}
#install openocd
brew install open-ocd
#install SRecord
brew install srecord
#install gcc
brew tap PX4/homebrew-px4
brew update
brew install gcc-arm-none-eabi-48
{% endhighlight %}

##Blinking led

###Connecting programmer

###Program

###Connecting diode

###Troubleshooting 

More info about wiring:
https://github.com/RIOT-OS/RIOT/wiki/Board%3A-yunjia-nrf51822



[1]: https://www.nordicsemi.com/eng/Products/Bluetooth-Smart-Bluetooth-low-energy/nRF51822
[2]: http://developer.mbed.org/platforms/Nordic-nRF51822/
[3]: http://www.wvshare.com/product/Core51822.htm
[4]: https://www.nordicsemi.com/eng/Products/Bluetooth-Smart-Bluetooth-low-energy/nRF51822-Development-Kit
[5]: https://www.nordicsemi.com/eng/Products/nRF51-DK
[6]: http://www.st.com/web/catalog/tools/FM146/CL1984/SC724/SS1677/PF251168
[7]: http://www.micromouseonline.com/2014/01/05/mini-st-linkv2-programmer/
[8]: http://www.silabs.com/products/interface/usbtouart/Pages/usb-to-uart-bridge.aspx
[9]: http://openocd.sourceforge.net
[10]: https://launchpad.net/gcc-arm-embedded
[11]: http://srecord.sourceforge.net

[99]: https://developer.mbed.org/handbook/Debugging

[Core51822]: /img/posts/general/core51822.jpg  "Cheap development board for nRF51822"
[ST-Link V2 mini]: /img/posts/general/stlinkv2.jpg  "ST-Link V2 mini programmer"
[Mini CP2102]: /img/posts/general/cp2102.jpg "Mini CP2102 USB 2.0 to UART"
[Breadboard]: /img/posts/general/breadboard.jpg "Breadboard with some wires"