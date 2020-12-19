# Build guide for R2 duckboard

Here is a comprehensive build guide for R2 duckboard, written by doodboard. 

## Table of Contents

* [components](#components)
* [flashing](#flashing)
* [LEDs](#leds)
* [diodes](#diodes)
* [hotswap sockets](#hotswap-sockets)
* [rotary encoder](#rotary-encoder)
* [ProMicro](#promicro)
* [top plate](#top-plate)
* [OLED](#oled)
* [assembly](#assembly)

<br/>

## components

### A single duckboard kit includes the following:

![component-1](https://github.com/doodboard/tutorial/blob/main/component_1.jpg)

a - diode x 22

b - M2 bolts and nuts / 4 short standoffs / 4 long standoffs

c - LEDs x 8 

d - kailh hotswap sockets x 21 

<br/>

e - encoder knob x 1 

f - rotary encoder x 1

<br/>

g - top plate x 1 

h - PCB x 1 

i - bottom plate x 1 

<br/>

j - pro micro x 1 

k - OLED x 1 

<br/>
<br/>

### A single acrylics case kit includes the following:

![component-2](https://github.com/doodboard/tutorial/blob/main/component_2.jpg)

l - acrylics top plate x 1 

m - acrylics plate x 1 

n - acrylics boundary (small holes) x 1 

o - acrylics boundary (big holes) x 1 

p - acrylics bottom plate x 1 

<br/>
<br/>

![component-3](https://github.com/doodboard/tutorial/blob/main/component_3.jpg)

q - M3 16mm screw  x 4 

r - M3 pop nuts x 4 

<br/>
<br/>

## flashing

### Please flash and test your promicro before starting the build!

You can download the hex file for R2 duckboard [here](https://officialdoodboard.netlify.app/support/duckboard_R2_default.hex)

If you wish to compile your own hex file, you can grab the source code [here](https://github.com/doodboard/source-code)

You can grab QMK toolbox from [here](https://github.com/qmk/qmk_toolbox)

![qmk_toolbox1](https://github.com/doodboard/tutorial/blob/main/qmk_toolbox_1.jpg)

1. confirm you have downloaded and opened the right HEX file on qmk toolbox
2. MCU should be set to "atmega32u4"
3. check Auto-Flash

<br/>

Plug in your pro micro, and if it doesn't flash automatically, short GND to RST on pro micro twice, fast.
Use a tweezer or a plier or anything conductive.

You should see the following if everything went successfully.

![qmk_toolbox2](https://github.com/doodboard/tutorial/blob/main/qmk_toolbox_2.jpg)

<br/>
<br/>

## LEDs 

### Now we'll work on the LEDs. This is the *toughest* part of the build. 

The LEDs are SMD, meaning they are surface mounted, as opposed to through hole mounted. 
Therefore, using flux is highly recommended as it helps solder to flow under the LEDs far more easily.

LEDs provide underglow to the duckboard. If you find it too furstrating, it's alright to forego the LEDs. 
It won't affect the core functionality of duckboard as a macropad.

![LED1](https://github.com/doodboard/tutorial/blob/main/LED_1.jpg)

LEDs should be positioned as shown above, the small black square inside the LED should line up with the small circle on the PCB.

<br/>

[This](https://streamable.com/dimwli) is how I solder the LEDs.
1. apply flux to both the PCB and the LED with a brush
2. set the soldering iron to 300C to prevent burning out the LEDs
3. place LED on the PCB. Make sure it's positioned correctly on the pads.
4. apply a small amount of solder to the soldering iron
5. make a short swiping motion perpendicular to the LED
6. repeat for all 4 pads.

<br/>

![LED3](https://github.com/doodboard/tutorial/blob/main/LED_3.jpg)

The finished solder joints should look like the photo above. You are aming for the nice slope of solder, not a blob.
Please make sure you only make contact wiht the iron for 2-3 seconds at a time. Longer exposure to heat can burn out the LED.

<br/>
<br/>

## diodes

### Next step is installing the diodes. 

![diode1](https://github.com/doodboard/tutorial/blob/main/diodes.jpg)

Nothing fancy here. Align the diodes as shown above, and solder them in. I recommend using flux, but it's not required.
There are total of 22 diodes to install: 21 for the 21 switches, and 1 for the push function of rotary encoder.

If you plan to use stabilisers, pay extra attention to the diodes near stab housings. 
You should clip the diode legs flush to the PCB in order to prevent clearing issue. 

<br/>
<br/>

## hotswap sockets

### And now onto the hotswap sockets.

![hotswap1](https://github.com/doodboard/tutorial/blob/main/hotswap_1.jpg)

Again, nothing fancy here. Place the hotswap sockets into the PCB, following the guidelines. 
If you prefer to solder your switches directly, you can skip this process, and solder in the switches later **after** installing the top plate.
Depending on if you would like to use duckboard as full 1u macropad, or as standard numpad, you should solder your hotswap sockets accordingly.

<br/>
<br/>

## rotary encoder

### Fun fun fun!

![encoder](https://github.com/doodboard/tutorial/blob/main/encoder_1.jpg)

No fancy tricks. Solder 7 spots circled above. Make sure the encoder is sitting flush to the PCB before you solder it.
The two tabs in the middle are for structural purposes only. Apply solder generally. 
The thinner legs to the top and bottom are malleable. Bend them a little if they need to be in order to fit the PCB.

<br/>
<br/>

## ProMicro

### Now the real fun begins.

![promicro1](https://github.com/doodboard/tutorial/blob/main/promicro_1.jpg)

Again, I recommend using flux, but it's not required. Just makes your life a little easier.

a) Solder the legs to ProMicro. Note the longer side of the legs goes into the PCB <br/> 
b) Solder the ProMicro to the PCB <br/>
c) Cut off the pins as much as you can, without damaging your solder joints.

<br/>
<br/>

### Now is the time to verify your soldering skills. 
Plug in your duckboard to your PC via USB cable.
All 8 LEDs should light up by default. If only a few of them lights up, follow these steps:

Start working from LED_1. The signal line for LEDs are connected in serial to help you debugging.
For example, if none of your LEDs light up, try reflowing LED_1. 
If LED_1, 2 and 3 light up, but not 4, try reflowing LED_3 and 4 until 4 lights up.

Default color for LED is RED with default R2 hex file. If some of your LEDs light up in diffrent colour, it's due to corrupted signal caused by bad solder joints.
If some of your LEDs work, but not in serial, so for insance LED_1, 2 and 8 light up, the same principle applies. Work on LED 2 and 3 until 3 lights up.

![promicro2](https://github.com/doodboard/tutorial/blob/main/promicro_2.jpg)

This is the schematic of the LED wiring for reference.

<br/>

![hotswap2](https://github.com/doodboard/tutorial/blob/main/hotswap_2.jpg)

This is also the perfect time to test your keypresses. You can either plug in the switches to test the keystrokes, or manually short the hotswap sockets. 

To test without switches, short the blue circles if you have the hotswap sockets installed. Short the yello circles if you plan to solder the switches in directly.

<br/>

![good soldering](https://cdn-learn.adafruit.com/assets/assets/000/001/978/large1024/tools_Header_Joints.jpg?1396777967)
If you have any issues, first make sure your LEDs and diodes are oriented right, then check your soldering joints to see if they all look ok.
Here is a reference image in courtesy of adafruit. 

<br/>
<br/>

## top plate

### Almost time to wrap it all up!

![top plate](https://github.com/doodboard/tutorial/blob/main/topplate.jpg)

Install stabilisers if you wish to use them. For 2u switches, I personally prefer the tactility of not having stabs installed, but that's just my personal opinion. 
You should install them now before moving on. Place the 4 screws into the plate, and screw in the shorter standoffs. 
Place the top plate onto the PCB, and screw in the longer standoffs.
You may find it easier to hold the standoffs with a plier while screwing them in place.

<br/>
<br/>

## OLED

### Almost time to wrap it all up!

<br/>
<br/>

## assembly