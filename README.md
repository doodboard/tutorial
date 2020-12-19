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

a - diode x 21 

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

You can grab QMK toolbox from [here](https://github.com/qmk/qmk_toolbox)

![qmk_toolbox](https://github.com/doodboard/tutorial/blob/main/qmk_toolbox_1.jpg)

1. confirm you have downloaded and opened the right HEX file on qmk toolbox
2. MCU should be set to "atmega32u4"
3. check Auto-Flash

Plug in your pro micro, and if it doesn't flash automatically, short GND to RST on pro micro twice, fast.
Use a tweezer or a plier or anything conductive.

You should see the following if everything went successfully.

![qmk_toolbox](https://github.com/doodboard/tutorial/blob/main/qmk_toolbox_2.jpg)


<br/>
<br/>

## LEDs

### Now we'll work on the LEDs. This is the *toughest* part of the build. 



## diodes

## hotswap sockets

## rotary encoder

## ProMicro

## top plate

## OLED

## assembly