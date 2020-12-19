# Build guide for R2 duckboard

Here is a comprehensive build guide for R2 duckboard, written by doodboard. 

## Table of Contents

* [components](#components)
* [flashing](#flashing)
* [LEDs](#leds)
* [diodes](#diodes)
* [hotswap sockets](#sockets)
* [rotary encoder](#encoder)
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

![diode1](https://github.com/doodboard/tutorial/blob/main/diode_1.jpg)

Nothing fancy here. Align the dioded as shown above, and solder them in. 
There are total of 22 diodes to install: 21 for the 21 switches, and 1 for the push function of rotary encoder.

<br/>
<br/>

## ProMicro

## hotswap sockets

## rotary encoder



## top plate

## OLED

## assembly