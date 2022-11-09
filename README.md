# Nixie Tube Clock

This document is intended to explain the technical details of my nixie tube clock, while also providing a rough overview of the journey I took to make this product a reality. Do note that this is my first fully completed project, and as well as my first time using many pieces of equipment. As such, take my process as a loose guideline instead of a set of instructions. Hopefully this write-up will help people avoid some of the mistakes I made during this project, and give people a look into the evolution of ideas during its creation. 

# Table of Contents
*   [Photo Gallery](#photo-gallery)
*   [Inspiration](#inspiration)
*   [Planning and Research](#planning)
*   [Components](#components)
    *   [Nixie Tubes: IN-12A](#nixie-tubes-in-12a)
    *   [Exixe Nixie Driver](#exixe Drivers)
    *   [Necessary PCBs](#necessary pcbs)
       *   [HV PSU: YanZeyuan’s NCH6100HV](#hv-psu-yanzeyuans-nch6100hv)
       *   [LV PSU: DROK LM2596](#lv-psu-drok-lm2596)
 *   [Design](#design)
    *   [Scrapped Features](#scrapped-feature) 
    *   [Woodworking](#woodworking)
    *   [Wiring](#wiring)
       
*   [Assembly](#assembly)
    *   [3d Print Plate](#3d-print-plate-for-pcbs)
    *   [Maple Wood Enclosure](#maple-wood-enclosure)
    *   [Walnut Wood Faceplate](#faceplate)
*   [Programming](#programming)
    *   [Libraries](#requirements)
    *   [Driving The Tubes](#tube-driving)
    *   [Reading The Time](#RTC)
*   [Animations](#animations)
    *   [Depth Transition](#depth-transition)
    *   [Number Transition](#number-transition)
*   [Future Work](#future-work)
*   [Credits](#credits)

# Inspiration
During the winter of 2021, I was looking for a new side project to work on over the holidays when I found [IllyaMoskvin's nixie tube display](https://github.com/IllyaMoskvin/nixie-counter). Along with this video by the channel [GreatScott!](https://www.youtube.com/watch?v=ObgmVNV1Kfg), I began research into making this idea a reality. Big thanks to IllyaMoskvin in particular for their great write-up detailing their work. I looked at tons of nixie tube clocks online to find inspiration for the aesthetics of the build, and I finally settled upon [Neonix's clock](https://www.neonix.one/en#buy) as the product I wanted to emulate. The curved corners complemented the rounded edges of the display and I especially liked the slight inset of the wooden faceplate in the aluminum body. Neonix's clock also contained many useful features that I wanted to include as well. In my ideal world, the clock would have an alarm function with custom music, 3 buttons (one snooze, and two to toggle time), and a web app to set an auto-turn-off time to preserve the life of the nixies. Looking back, that was very ambitious, and almost everything I had planned was eventually scrapped due to space, time and cost constraints. 

# Planning and Research
It quickly became obvious that an aluminum body would be impractical for the project at hand. The raw material along with the anodization process would be prohibativly expensive, and finding a shop to learn how to machine was not feasible. The electronics part of the project would be the most comfortable for me, as I have the most experience in this area. Nixie tubes require around 170V DC to run, meaning that I need to purchase a boost converter to step up the 12V from a DC barrel jack to 170V. Additionally, each Nixie tube has 10 pins,  I bought 4 [exixe driver boards](https://www.tindie.com/products/dekuNukem/exixe-miniture-nixie-tube-driver-modules/#product-reviews) for $13 each, 4 [in12-b nixie tubes](https://www.ebay.com/itm/131964707917?hash=item1eb9b5a44d:g:C3cAAOSwmLlX-i1o) for $4 each, and the rest of the products, I already had leftover from other products. (The full parts list and price can be found [here](https://docs.google.com/spreadsheets/d/13VwZzKPhzOkpslhoitIj5g3k4Q4i2Dl7qZcKzXsNUyM/edit?usp=sharing))
