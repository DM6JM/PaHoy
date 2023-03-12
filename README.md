# PaHoy

This project aims to have a neat integration of a nRF24L01+ into a Raspberry Pi 4B based system.
Background of the project is the use of [aHoy](https://github.com/lumapu/ahoy) with a RasPi to monitor Hoymiles Solar-Inverters. Most solutions are rather fiddly with open wiring and no fitting case.
To overcome these issues, I (DM6JM) created the **PaHoy**: 
+ A small PCB containing everything to smoothly connect the nRF24L01+ to the PI using its 40pin Dev-Block
+ Using standard pinning, so most code doesn't need any adjustment
+ Comes with an u-FL connector, so you may connect any 50-Ohm 2.4GHz antenna you want.
+ And, biggest plus, to fit into the [CoolerMaster Pi Case 40 V2](https://www.coolermaster.com/de/de-de/catalog/gehause/raspberry-pi/pi-case-40-v2/)

## How is this done? 
The [CoolerMaster Pi Case 40 V2](https://www.coolermaster.com/de/de-de/catalog/gehause/raspberry-pi/pi-case-40-v2/) has a small internal PCB, the sits on the 40-pin Dev-Block of the Pi and routes these pins in an 90degree angle to the outside of the case. I just took the dimensions of this PCB and replaced it by the **PaHoy** PCB. 

## Assembly
Before starting assembly: Make sure you are properly grounded in some way! ESD will kill the PCB and maybe the Pi as well, so pay attention. Use a wrist-wrap or other means of discharging yourself properly!
+ Before turing it on for the first time, double check that all parts are soldered correctly. A flipped IC might short your IOs of the Pi and cause damage!
+ Remove the original PCB out of the case by releasing the screw and the two distance bolts.
+ If you want to use an antenna built directly into the case, I recommend [this antenna by Linx](https://www.digikey.de/de/products/detail/linx-technologies-inc/ANT-2-4-PW-QW-UFL/4747969). It can be ordered together with the special low height 40pin connector at Digikey or Mouser (see Ordering). If applicable, drill the mounting hole into the Pi case and remove any left strands carefully. Mount the antenna in place and pay attention to already check if the antenna's u.FL connector is oriented the right way, so that it can be attached to the PCB later easily.
+ Before assembling everything togheter, it might make sense to run a dry check.

![Dry check of a prototype](/PaHoy\Docu\Pictures_Assembly/Proto1.JPG "Proto1")
![Dry check of a prototype](/PaHoy\Docu\Pictures_Assembly/Proto2.JPG "Proto2")

+ If you can talk to the nRF24L01+, go ahead with assembly. Mount the **PaHoy** the same way the original PCB has been mounted before. Do not overtight the screw and the distance bolts!
+ Before putting the Pi on top of the **PaHoy**, check the RF-wire to the antenna one last time. Is it routed properly within the case? (The antenna recommended above has a quite long cable for what is needed inside the case.) It must not be folded, bent or routed in small diameters and should not be sqeezed in between somewhere. Open the rubber lid at the side an check if the u.FL connector sits properly on the PCB's counterpart?

![Check antenna wiring](/PaHoy\Docu\Pictures_Assembly/Assemb1.JPG "Antenna wiring")
![Check connector](/PaHoy\Docu\Pictures_Assembly/Assemb2.JPG "Connector")

+ If everything is alright, mount the Pi and before closing the lid, make one final check if the RF cable is still where it should be. (E.g. not squished above the USB ports). Once the case is closed, attach power and enjoy the nRF24L01+ for your project!

## Data
The project has been done in Altium, but Gerbers, Schematics as PDF and alle production data is in the repo, so you can use it also without having an Altium licence. Pay attention, the PCB is just 1.2mm in height! Otherwise it doesn't fit.

## Ordering
Right now, there is no commercial way of buying these PCBs and I can't name any shop. I don't supply them by myself, since I got no registered business. 
I can just recommend the way of ordering I went through:
+ Take the Gerbers, the BOM and the PicknPlace data and head over to JLC-PCB. They offer cheap PCB service and assembly in a one-stop-manner. Get familiar with how their service works (e.g. buying the parts before starting the PCB and assembly order) and let them do it. All my prototypes where made by them and apart from one mistake (wrong PicknPlace data from my side) I had never an issue with them. When ordering there, always choose "review assembly data", so that you have a chance to see the IC orientation in their tools. The nRF24L01+ is flipped every time. You then have the chance to correct it.
+ The data (BOM, PicknPlace) is already prepared to comply with JLCPCB partnumbering, so you can start right away.
+ JLCPCB can assembly only on one side. SMT-side is bottom in this case. The 40pin connector towards the Pi has to be soldered by yourself. It is hard to get, since it is of lower hight than standard 100mil connectors. You can order it at Digikey or Mouser (both supply also private customers), P/N M20-7812045.
+ When ordering the PCB, pay attention, the PCB is just 1.2mm in height, otherwise it won't fit into the case properly!
