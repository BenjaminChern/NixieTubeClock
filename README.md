# Nixie Tube Clock

This document is intended to explain the technical details of my nixie tube clock, while also providing a rough overview of the journey I took to make this product a reality. Do note that this is my first fully completed project, and as well as my first time using many pieces of equipment. As such, take my process as a loose guideline instead of a set of instructions. Hopefully this write-up will help people avoid some of the mistakes I made during this project, and give people a look into the evolution of ideas during its creation. 

# Table of Contents
*   [Photo Gallery](#photo-gallery)
*   [Inspiration](#inspiration)
*   [Planning and Research](#planning-and-research)
    *   [Design](#design)
    *   [Wiring Diagram](#wiring-diagram)
*   [Components](#components)
    *   [Nixie Tubes: IN-12A](#Nixie-Tubes)
    *   [Exixe Nixie Driver](#Exixe-Nixie-Driver)
    *   [Other PCBs](#other-pcbs)
*   [Assembly](#assembly)
    *   [Maple Wood Enclosure](#maple-wood-enclosure)
    *   [Walnut Wood Faceplate](#faceplate)
*   [Programming](#programming)
    *   [Libraries](#requirements)
    *   [Driving The Tubes](#tube-driving)
    *   [Reading The Time](#RTC)
*   [Animations](#animations)
*   [Future Work](#future-work)
*   [Credits](#credits)

# Inspiration
During the winter of 2021, I was looking for a new side project to work on over the holidays when I found [IllyaMoskvin's nixie tube display](https://github.com/IllyaMoskvin/nixie-counter). Along with this video by the channel [GreatScott!](https://www.youtube.com/watch?v=ObgmVNV1Kfg), I began research into making this idea a reality. Big thanks to IllyaMoskvin in particular for their great write-up detailing their work. I looked at tons of nixie tube clocks online to find inspiration for the aesthetics of the build, and I finally settled upon [Neonix's clock](https://www.neonix.one/en#buy) as the product I wanted to emulate. The curved corners complemented the rounded edges of the display and I especially liked the slight inset of the wooden faceplate in the aluminum body. In my ideal world, the clock would have an alarm function with custom music, 3 buttons (one snooze, and two to toggle time), and a web app to set an auto-turn-off time to preserve the life of the clock. Looking back, that was very ambitious, and almost everything I had planned was eventually scrapped due to space, time and cost constraints. 

# Planning and Research
It quickly became obvious that an aluminum body would be impractical for the project at hand. The raw material along with the anodization process would be prohibativly expensive, and finding a shop to learn how to machine was surprisingly difficult. In the future, I still want to learn to machine metal, however this project uses only wood for its exterior. Learning woodworking is much easier and there are a few makerspaces around the Atlanta area that teach woodworking. Big thanks to [Decatur Makers](https://decaturmakers.org) and the staff for their help and guidance, I really could not have done the project without them. Lastly, the electronics part of the project was much more comfortable for me due to my experience in this area. Other than the 170 volts to drive the tubes, I had worked with or heard of all the other components. However, there is an entire section dedicated to the electronics below so I will cover it in detail later. Once finished with a parts list and preliminary design, I ordered the parts and began to work on the design. 

## Design 
The housing design is mostly based off [this](www.etsy.com/listing/751460311) etsy listing. The faceplate and body were designed in Fusion360 however, I ended up changing the original design by quite a lot while sanding the product down. If I were to do it again, I would definitly add 1/8 to 1/4 on both sides, as the fit for the electronics is extremely tight. Unfortunately I lost the files when transferring my Fusion360 account to a different email but I do have the dimensions of most of the relevant parts. Also, the dimensions of the nixie tubes can be found [here](http://www.tube-tester.com/sites/nixie/dat_arch/IN-12A_IN-12B_03.pdf). 
   * **Faceplate**
     * Height-
     * Width-
     * Thickness-
     * Corner Fillet-
  * **Body**
     * Length-
     * Width-
     * Height-
     * Thickness-

## Wiring Diagram
At the time, I did not understand how to create wiring diagrams so I do not have anything proper for others to use. However I do have a picture of the diagram I used for much of the project. Do be warned though that it is quite messy and will probably not be much help. In essence the DC barrel jack outputs 14v which powers the arduino, the 170 volt boost converter, and a board that outputs 3.3 volts. The 3.3 volts and 170 volts are connected to the driver boards in parallel and while the SDA, SCL, and PINOUT lines on the arduino are connected to the boards in parallel. Finally all of the boards are grounded to a common ground. 

# Components
Most of these parts are off-the-shelf products from places like Amazon or Digikey except for the driverboard. I have no complaints with any of these components and if I were to build this again, I would honestly order the same things. 

## Nixie Tubes
The 2 most common nixie tubes are the IN-12 and the IN-14 models. Both have decent documentation surrounding them, but the documentation most likely apply to rarer models like IN-1 and IN-19 tubes. These tubes were purchased on ebay from a Ukranian reseller before the war who is unfortunatly no longer in business. I purchased tubes that were NOS standing for "New Old Stock" meaning that they were never opened/used before. When they arrived, they were in perfect condition and I would reccomend purchasing NOS for anyone attempting the same thing.  

## Exixe Nixie Driver
This driver board was the heart of the project and the hardest to source. Many existing drivers for the IN12 were too large and didn't fit the form factor that I wanted to use. Its possible to create a custom driver using shift registers as seen [here](https://www.instructables.com/Driving-two-Nixie-tubes-with-an-Arduino-via-a-shif/) but this was outside of my ability at the time, not to mention the mess of wires necessary for a non PCB approach. After some research, I found [this](https://www.tindie.com/products/dekuNukem/exixe-miniture-nixie-tube-driver-modules/) product which suited my needs(Big thanks to dekuNukem in the UK for creating this). With this driver, setup became a lot easier and a very helpful setup guide was provided which can be found [here](https://github.com/dekuNukem/exixe). The board has tons of great features including RGB backlights, PWM to control the brightness, and best of all, it used the SPI interface which made wiring much easier in comparison to the shift register approach. 

## Other PCBs

There is not much to say about the other PCBs. The [NCH6100HV](https://www.ebay.com/itm/144301291333) recieves 14 volts from the DC barrel jack powering the whole clock and steps it up to 170V DC, powering the tubes while the [DROK lm2596](https://www.amazon.com/Converter-DROK-Immersion-Regulator-Transformer/dp/B078XQ5MWR/ref=sr_1_3?crid=1DIDPEJEBNTMV&keywords=drok+lm2596+dc+to+dc+buck+converter&qid=1637119219&sprefix=drok+lm%2Caps%2C165&sr=8-3) buck converter steps down the 14 volts to 3.3 in order to power the driver boards. The only complaint is that the DROK has a really bright green indicator LED on the board which slightly glows in the clock body. This was easily fixed with a few layers of black electrical tape though. 

# Assembly

This was by far the most time consuming part of the process. I had little experience with soldering and no experience with woodworking. Regardless, everything turned out fine and I am suprised with how well it went for my first time. In order to fit all the wiring into such a cramped space, I spliced multiple dupont wires together in order to create data-lines from the driver boards to the arduino. The result is quite cursed and most definately 
