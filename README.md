# Nixie Tube Clock

This document is intended to explain the technical details of my nixie tube clock, while also providing a rough overview of the journey I took to make this product a reality. Hopefully this write-up will help people avoid some of the mistakes I made during this project, and give people a look into the ideas I had to cut over time order to make this. 

# Table of Contents
*   [Photo Gallery](#photo-gallery)
*   [Inspiration](#inspiration)
*   [Planning](#planning)
*   [Design](#design)
    *   [Scrapped Features](#scrapped-feature) 
    *   [Woodworking](#woodworking)
    *   [Wiring](#wiring)
*   [Components](#components)
    *   [Nixie Tubes: IN-12A](#nixie-tubes-in-12a)
    *   [Exixe Nixie Driver](#exixe Drivers)
    *   [Necessary PCBs](#necessary pcbs)
       *   [HV PSU: YanZeyuan’s NCH6100HV](#hv-psu-yanzeyuans-nch6100hv)
       *   [LV PSU: DROK LM2596](#lv-psu-drok-lm2596)
       
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
During the winter of 2021, I was looking for a new arduino project to work on over the holidays when I stumbled across a reddit post leading to [IllyaMoskvin's nixie tube display](https://github.com/IllyaMoskvin/nixie-counter). I had already seen a video about the subject 3 months ago by the youtube channel [GreatScott!](https://www.youtube.com/watch?v=ObgmVNV1Kfg) and because of these two events, I decided to venture deeper into the subject of nixie tubes. I looked at tons of nixie tube clocks online to find inspiration and I finally settled upon [Neonix's clock](https://www.etsy.com/listing/931590165/nixie-tube-clock-neonix-412-customizable?ga_order=most_relevant&ga_search_type=all&ga_view_type=gallery&ga_search_query=nixie+tube+clock&ref=sc_gallery-1-5&plkey=ac1318e828d258e6cba0e64b21e83669887453da%3A931590165&frs=1&sts=1) as the product I wanted to emulate because it looked the most polished out of any clock I had seen so far. In my ideal world, the clock had an alarm function with custom music, 3 buttons, one snooze, and two to toggle time, and a web app to set an auto-turn-off time to preserve the life of the nixies. However, almost everything I had planned was eventually scrapped due to space, time and cost constraints. 

# Planning 
In my mind, this project was split into 3 parts. Metalworking, Woodworking and Electronics. The electronics part of the project would be the most comfortable for me, as I have the most experience in this area. I bought 4 [exixe driver boards](https://www.tindie.com/products/dekuNukem/exixe-miniture-nixie-tube-driver-modules/#product-reviews) for $13 each, 4 [in12-b nixie tubes](https://www.ebay.com/itm/131964707917?hash=item1eb9b5a44d:g:C3cAAOSwmLlX-i1o) for $4 each, and the rest of the products, I already had leftover from other products. (The full parts list and price can be found [here](https://docs.google.com/spreadsheets/d/13VwZzKPhzOkpslhoitIj5g3k4Q4i2Dl7qZcKzXsNUyM/edit?usp=sharing))
