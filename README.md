# Nixie Tube Clock

This document is intended to explain the technical details of my nixie tube clock, while also providing a rough overview of the journey I took to make this product a reality. Do note that this is my first fully completed project, and as well as my first time using many pieces of equipment. As such, take my process as a loose guideline instead of a set of instructions. Hopefully this write-up will help people avoid some of the mistakes I made during this project, and give people a look into the evolution of ideas during its creation. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/61395558/213846743-f7aa4a15-e72a-4817-91e3-f61856b371e3.jpg" width=90% height=90%">
</p>

    
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
*   [Animation](#animation)
*   [Future Work](#future-work)
*   [Credits](#credits)

# Photo Gallery
                                                                                                                                        
<div style="display:flex">
     <div style="flex:1;padding-right:10px;">
          <img src="https://user-images.githubusercontent.com/61395558/213847010-740acd19-e42b-431b-9e02-1d8d7db48735.jpg" width="350"/>
     </div>
     <div style="flex:1;padding-left:10px;">
          <img src="https://user-images.githubusercontent.com/61395558/213847047-079c2e90-cb61-4a59-bde4-73f682b18211.jpg" width="350"/>
     </div>
     <div style="flex:1;padding-left:10px;">
          <img src="https://user-images.githubusercontent.com/61395558/213846743-f7aa4a15-e72a-4817-91e3-f61856b371e3.jpg" width="350"/>
     </div>
</div>
                                                                                                                                        
# Inspiration
During the winter of 2021, I was looking for a new side project to work on over the holidays when I found [IllyaMoskvin's nixie tube display](https://github.com/IllyaMoskvin/nixie-counter). Along with this video by the channel [GreatScott!](https://www.youtube.com/watch?v=ObgmVNV1Kfg), I began research into making this idea a reality. Big thanks to IllyaMoskvin in particular for their great write-up detailing their work. I looked at tons of nixie tube clocks online to find inspiration for the aesthetics of the build, and I finally settled upon [Neonix's clock](https://www.neonix.one/en#buy) as the product I wanted to emulate. The curved corners complemented the rounded edges of the display and I especially liked the slight inset of the wooden faceplate in the aluminum body. In my ideal world, the clock would have an alarm function with custom music, 3 buttons (one snooze, and two to toggle time), and a web app to set an auto-turn-off time to preserve the life of the clock. Looking back, that was very ambitious, and almost everything I had planned was eventually scrapped due to space, time and cost constraints. 

# Planning and Research
It quickly became obvious that an aluminum body would be impractical for the project at hand. The raw material along with the anodization process would be prohibativly expensive, and finding a shop to learn how to machine was surprisingly difficult. In the future, I still want to learn to machine metal, however this project uses only wood for its exterior. Learning woodworking is much easier and there are a few makerspaces around the Atlanta area that teach woodworking. Big thanks to [Decatur Makers](https://decaturmakers.org) and the staff for their help and guidance, I really could not have done the project without them. Lastly, the electronics part of the project was much more comfortable for me due to my experience in this area. Other than the 170 volts to drive the tubes, I had worked with or heard of all the other components. However, there is an entire section dedicated to the electronics below so I will cover it in detail later. Once finished with a parts list and preliminary design, I ordered the parts and began to work on the design. 

## Design 
<img width="567" alt="Screen Shot 1" src="https://user-images.githubusercontent.com/61395558/213847858-44ef55a9-8311-491c-b55c-5490ffc47361.png">

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
<p align="left">
  <img src="https://user-images.githubusercontent.com/61395558/213847691-8c291b48-8104-444c-942a-8e9b377d7e18.jpg" width=60% height=50%">
</p>

At the time, I did not understand how to create wiring diagrams so I do not have anything proper for others to use. However I do have a picture of the diagram I used for much of the project. Do be warned though that it is quite messy and will probably not be much help. In essence the DC barrel jack outputs 14v which powers the arduino, the 170 volt boost converter, and a board that outputs 3.3 volts. The 3.3 volts and 170 volts are connected to the driver boards in parallel and while the SDA, SCL, and PINOUT lines on the arduino are connected to the boards in parallel. Finally all of the boards are grounded to a common ground. 

# Components
<p align="left">
  <img src="https://user-images.githubusercontent.com/61395558/213847820-7f668c7a-fa5d-4c33-bce5-2fe52b6ff2d6.jpg" width=60% height=50%">
</p>

Most of these parts are off-the-shelf products from places like Amazon or Digikey except for the driverboard. I have no complaints with any of these components and if I were to build this again, I would order the same things. 

## Nixie Tubes
The 2 most common nixie tubes are the IN-12 and the IN-14 models. Both have decent documentation surrounding them, but the documentation most likely applies to rarer models like IN-1 and IN-19 tubes. These tubes were purchased on ebay from a Ukranian reseller before the war who is unfortunatly no longer in business. I purchased tubes that were NOS standing for "New Old Stock" meaning that they were never opened/used before. When they arrived, they were in perfect condition and I would reccomend purchasing NOS for anyone attempting the same thing.  

## Exixe Nixie Driver
This driver board was the heart of the project and the hardest to source. Many existing drivers for the IN12 were too large and didn't fit the form factor that I wanted to use. Its possible to create a custom driver using shift registers as seen [here](https://www.instructables.com/Driving-two-Nixie-tubes-with-an-Arduino-via-a-shif/) but this was outside of my ability at the time, not to mention the mess of wires necessary for a non PCB approach. After some research, I found [this](https://www.tindie.com/products/dekuNukem/exixe-miniture-nixie-tube-driver-modules/) product which suited my needs(Big thanks to dekuNukem in the UK for creating this). With this driver, setup became a lot easier and a very helpful setup guide was provided which can be found [here](https://github.com/dekuNukem/exixe). The board has tons of great features including RGB backlights, PWM to control the brightness, and best of all, it used the SPI interface which made wiring much easier in comparison to the shift register approach. 

## Other PCBs

There is not much to say about the other PCBs. The [NCH6100HV](https://www.ebay.com/itm/144301291333) recieves 14 volts from the DC barrel jack powering the whole clock and steps it up to 170V DC, powering the tubes while the [DROK lm2596](https://www.amazon.com/Converter-DROK-Immersion-Regulator-Transformer/dp/B078XQ5MWR/ref=sr_1_3?crid=1DIDPEJEBNTMV&keywords=drok+lm2596+dc+to+dc+buck+converter&qid=1637119219&sprefix=drok+lm%2Caps%2C165&sr=8-3) buck converter steps down the 14 volts to 3.3 in order to power the driver boards. The only complaint is that the DROK has a really bright green indicator LED on the board which slightly glows in the clock body. This was easily fixed with a few layers of black electrical tape. 

# Assembly
<p align="left">
  <img src="https://user-images.githubusercontent.com/61395558/213847892-572afab6-e4cf-4281-b2fb-8e73f19aa741.jpg" width=60% height=50%">
</p>

This was by far the most time consuming part of the process. I had little experience with soldering and no experience with woodworking. Regardless, everything turned out fine and I am suprised with how well it went for my first time. In order to fit all the wiring into such a cramped space, I spliced multiple dupont wires together in order to create data-lines from the driver boards to the arduino. The result is not suitable for long term applications, however it still is working for now. 

## Maple Wood Enclosure

The housing was the most difficult part of this project. I originally intended to use a CNC machine to hollow out a 6x6x3 inch block of wood found [here](https://www.rockler.com/plain-maple-turning-blanks). However after talking to people at my local makerspace, I was convinced to hollow the block out by hand. I started with the drill press and made 4 large holes at the corners with the biggest bit. After that, I went in with a hammer and chisel to remove the four edges. Along the way I cracked the outside slightly which was to be expected considering the method I was using. By this time I was already frustrated with the slow pace but that was nothing compared to the sanding process. I sanded the same block of wood for about 16 hours spread over the course of 3 days. I was so scared of cracking the outside that I sanded down a whole inch worth of maple on both sides by the time I was done. The pain was worth it though, as I really enjoy how the final result looks and I call it a sucess for my first woodworking project. 
<p align="left">
  <img src="https://user-images.githubusercontent.com/61395558/213848224-83fa51c0-f8f0-4687-a731-4d0249a67e0f.png" width=50% height=50%">
</p>


## Walnut Wood Faceplate 

<p align="left">
  <img src="https://user-images.githubusercontent.com/61395558/213848262-a905c5e8-e4c7-47f3-8636-b11744e8b276.jpg" width=50% height=50%">
</p>

This luckily was much simpler than the housing. I modeled the faceplate in Fusion360 and sent the design to the laser cutter. When laser cutting, I advise putting masking tape on the surface of the wood which completely eliminates burn marks around the outside of the cut. I would highly reccomend this technique to anyone laser cutting a piece that needs to look aesthetic. To finish both the faceplate and the body, I wiped it down with mineral oil and then applied 2 coats of tung oil finish 4 days apart.

# Programming

Compared to the rest of this project, the code was simple. I finished this in a day and it was a nice break from the physical construction of this project. The code runs on a arduino nano which is perfect for the project. The code uses the "RTCLib.h" and "exixe.h" libraries from arduino and nothing else. All the code for driving the nixie tubes can be found in the previous link to dekuNukem's github page where they lay out a comprehensive guide to setup. Finally I will post the code here although it is VERY messy and the logic is unoptimized. 

```
/*
  exixe modules:
  https://github.com/dekuNukem/exixe

  library docs:
  https://github.com/dekuNukem/exixe/tree/master/arduino_library

  Demo 5: Loop digits on two tubes with crossfade animation
*/

#include "exixe.h"
#include "RTClib.h"

RTC_DS3231 rtc;

// change those to the cs pins you're using
int cs1 = 7;
int cs2 = 8;
int cs3 = 9;
int cs4 = 10;
int brightness = 90; 
unsigned char count;
byte currMin;

exixe my_tube1 = exixe(cs1); //tens hour
exixe my_tube2 = exixe(cs2); //ones hour
exixe my_tube3 = exixe(cs3); //tens minute
exixe my_tube4 = exixe(cs4); //ones minute

DateTime past; 

void setup()
{
   Serial.begin(9600); 
  // ONLY CALL THIS ONCE
  my_tube1.spi_init();

  my_tube1.clear();
  my_tube2.clear();
  my_tube3.clear();
  my_tube4.clear();

  rtc.begin();
  
 
   //rtc.adjust(DateTime(F(__DATE__),F(__TIME__)));  
   // ***NOTE*** rtc.adjust will remember the time that the sketch was uploaded, 
   //and every time it powers on, it will adjust the time BACK to the time of the upload
   //therefore run this line once and then NEVER again
  DateTime now = rtc.now();

  if(now.hour()>12){
      animateDepth((((now.hour()-12) / 10)%10), ((now.hour()-12)%10), ((now.minute() / 10)%10), ((now.minute())%10));
    }
    else if(now.hour() == 0){
      animateDepth(1, 2, ((now.minute() / 10)%10), ((now.minute())%10));
    }
    else{
      animateDepth(((now.hour()) / 10)%10, ((now.hour())%10), ((now.minute() / 10)%10), ((now.minute())%10));

    }
  currMin = now.minute(); 
}

void loop()
{
  DateTime now = rtc.now();
  if(now.minute() != currMin)
  {
    Serial.println("TIME CHANGE");
    if(now.hour()>12){
      animate((((now.hour()-12) / 10)%10), ((now.hour()-12)%10), ((now.minute() / 10)%10), ((now.minute())%10));
    }
    else if(now.hour() == 0){
      animate(1, 2, ((now.minute() / 10)%10), ((now.minute())%10));
    }
    else{
      animate(((now.hour()) / 10)%10, ((now.hour())%10), ((now.minute() / 10)%10), ((now.minute())%10));

    }
    currMin = now.minute(); 
    
  }
  Serial.print("current hour is: ");
  Serial.print(now.hour());
  Serial.print("current minute is: ");
  Serial.print(now.minute());
  Serial.print("current second is: ");
  Serial.println( now.second());
  
  
  delay(1000);
}
void animate(int tensHour, int onesHour, int tensMin, int onesMin)
{
  my_tube1.show_digit(9, 100, 0);
  my_tube2.show_digit(9, 100, 0);
  my_tube3.show_digit(9, 100, 0);
  my_tube4.show_digit(9, 100, 0);
  
  for(int i = 9; i>=0; i--)
  {
    if(i>=tensHour)
    {
      my_tube1.show_digit(i, 127, 0);
    }
     if(i>=onesHour)
    {
      my_tube2.show_digit(i, 127, 0);
    }
     if(i>=tensMin)
    {
      my_tube3.show_digit(i, 127, 0);
    }
     if(i>=onesMin)
    {
      my_tube4.show_digit(i, 127, 0);
    }
    delay(150);
  }
}
void animateDepth(int tensHour, int onesHour, int tensMin, int onesMin)
{
  my_tube1.show_digit(1, 100, 0);
  my_tube2.show_digit(1, 100, 0);
  my_tube3.show_digit(1, 100, 0);
  my_tube4.show_digit(1, 100, 0);
  int digitArray[] = {1, 6, 2, 7, 5, 0, 4, 9, 8, 3}; 
  bool flag1 = false;
  bool flag2 = false;
  bool flag3 = false;
  bool flag4 = false;
  
  for(int i = 0; i<10; i++)
  {
    if(digitArray[i] == tensHour)
    {
      my_tube1.show_digit(digitArray[i], 127, 0);
      flag1 = true;
    }
     if(digitArray[i] == onesHour)
    {
      my_tube2.show_digit(digitArray[i], 127, 0);
      flag2 = true;
    }
     if(digitArray[i] == tensMin)
    {
      my_tube3.show_digit(digitArray[i], 127, 0);
      flag3 = true;
    }
     if(digitArray[i] == onesMin)
    {
      my_tube4.show_digit(digitArray[i], 127, 0);
      flag4 = true;
    }
    else if (flag1 == false){
      my_tube1.show_digit(digitArray[i], 127, 0);
    }
    else if (flag2 == false){
      my_tube2.show_digit(digitArray[i], 127, 0);
    }
    else if (flag3 == false){
      my_tube3.show_digit(digitArray[i], 127, 0);
    }
    else if (flag4 == false){
      my_tube4.show_digit(digitArray[i], 127, 0);
    }
    delay(150);
  }
}  
```

# Animation
This is the animation I decided to use when the clock changes time. I think it looks quite nice. 
<p align="left">
  <img src="https://user-images.githubusercontent.com/61395558/213849102-415ec1cc-c5eb-4e2e-aff2-a5eab86c4bec.gif" width=60% height=50%">
</p>

# Future Works
Currently I am working on building a self playing piano. I am finished with the research phase and have recently ordered parts for my newest project. As of 11/08/23, I am finished with the project and am currently writing the documentation.

# Credits

Big thanks to IllyaMoskvin for being the inspiration for this writeup and providing tons of information along the way, DekuNukem for the nixie driver support, and the folks over at Decatur Makers for making this all possible 
