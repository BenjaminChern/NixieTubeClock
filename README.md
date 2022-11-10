# Nixie Tube Clock

This document is intended to explain the technical details of my nixie tube clock, while also providing a rough overview of the journey I took to make this product a reality. Do note that this is my first fully completed project, and as well as my first time using many pieces of equipment. As such, take my process as a loose guideline instead of a set of instructions. Hopefully this write-up will help people avoid some of the mistakes I made during this project, and give people a look into the evolution of ideas during its creation. 

# Table of Contents
*   [Photo Gallery](#photo-gallery)
*   [Inspiration](#inspiration)
*   [Planning and Research](#planning-and-research)
    *   [Design](#design)
    *   [Wiring](#wiring)
 *   [Components](#components)
     *   [Nixie Tubes: IN-12A](#nixie-tubes-in-12a)
     *   [Exixe Nixie Driver](#exixe Drivers)
     *   [Other PCBs](#other pcbs)
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
It quickly became obvious that an aluminum body would be impractical for the project at hand. The raw material along with the anodization process would be prohibativly expensive, and finding a shop to learn how to machine was not feasible. In the future, I still want to learn to machine metal, however this project uses only wood for its exterior. Luckily, there are a few makerspaces around the Atlanta area that teach woodworking so big thanks to [Decatur Makers](https://decaturmakers.org) and the staff for their help and guidance. The electronics part of the project was much more comfortable for me, as I have the most experience in this area. There is an entire section dedicated to the electronics below so I will cover it there. Once finished with a parts list and preliminary design, I ordered the parts and began to work on the design. 

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

## Wiring 
At the time, I did not understand how to create wiring diagrams so I do not have anything proper for others to use. However I do have a picture of the diagram I used for much of the project. Do be warned though that it is quite messy and will probably not be much help. In essence the DC barrel jack outputs 15v which powers the arduino, the 170 volt boost converter, and a board that outputs 3.3 volts. The 3.3 volts and 170 volts are connected to the driver boards in parallel and while the SDA and SCL lines on the arduino are connected to the boards in parallel. Finally all of the boards are grounded to a common ground.  
