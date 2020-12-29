# Duckboard FAQs

Please read the [main tutorial first](README.md).

## How do I flash my Pro Micro?

Plug it in with a Micro-USB DATA CABLE (some cables just deliver power) to your computer. If it is a data cable, you should hear a sound that shows that it is connected. Navigate to the QMK toolbox and load the appropriate `.hex` file. Check the autoflash box. On the Pro Micro, short the GND and RST pads (they’re the ones next to each other) together with a metal object (tweezers or a piece of solder bent into a U shape work well) twice as fast as you can. You'll see text on the screen, and it should end with doodboard/duckboard connected.

## Is there a way to reset the Pro Micro after I assembled the board?

If you haven’t flashed it already, then follow the steps from the previous question. If you have already flashed it, you should be able to reset it by navigating to the RGB layer and hitting the encoder knob.

## I soldered on the Pro Micro upside down! How do I remedy this?

If your Pro Micro is soldered upside down, you have a couple options:

1. (Recommended) Desolder the Pro Micro, either with a desoldering pump, desoldering gun, or wick.
2. If the Pro Micro is simply on the wrong side of the PCB, it is possible to rig up a solution to allow duck operation in the FR4 sandwich case to make it work, such as omit the top plate entirely.
3. Keep in mind the Pro Micro does not have a symmetrical pinout. If it is soldered in a rotated fashion, your board will simply not work. You must desolder if this happens.

## My LEDs aren't working?

All LEDs are wired in series. That means if LED 1 doesn't work, none of the LEDs work. 99% of the time, LEDs not working are going to be due to improper soldering. Watch the video linked in [the LED section of the build guide](README.md#leds) and reflow each LED, testing after each one to see how many work.

## Why are my keypresses delayed and laggy?

Because you haven't soldered the OLED in. The OLED waits for a keypress to respond, so if there is no OLED, there will conflict within the firmware. If you want to use the duckboard without the OLED for whatever reason, disable it in [`rules.mk`](https://github.com/doodboard/source-code/blob/main/duckboard_R2/rules.mk).

## How do I change what appears on the OLED?

In order to change the animation, you’re gonna need to turn a B/W image into a string of numbers. This website works: https://joric.github.io/qle/. Edit it in  [`keymap.c`](https://github.com/doodboard/source-code/blob/main/duckboard_R2/keymaps/default/keymap.c), and keep in mind the stock duck is 32x32 pixels and has 2 images.

## How do I make my own firmware?

To make your own firmware, or edit the preexisting one, you’ll need to have a code environment set up. Follow the QMK getting started doc here: https://beta.docs.qmk.fm/tutorial/newbs_getting_started. The basic applications you’ll need installed are: Python, MSYS, and a text editor of your choosing.

## My LEDs light up different colors/My LEDs aren’t red by default?

If your LEDs light up different colors, it’s due to the data pads on them being badly soldered. Each LED has 4 pads: `VCC` (power) `GROUND`, `DATA IN`, and `DATA OUT`. Discolored LEDs are due to the `DATA IN`/`OUT` pads having some kind of problem. Start with the first LED that is discolored (default for R2 firmware is red) and reflow the joints.

## My LEDs are all white/How do I change the colors?

This happens when the saturation on the board is turned up all the way. Navigate to the RGB layer (layout can be seen [here](https://i.imgur.com/bLKk2QL.jpg)) and hit the `RGB_SAT-` button a number of times. This will lower the saturation. After that is done, you should be able to change the colors of the LEDs by using `RGB_HUE-` and `RGB_HUE+`.

## My keypresses don’t work?

Follow this checklist to make your keypresses work:
1. Are your diodes installed? If so, are the black bars on them on the right side? The diodes are not reversible.
2. Are your Kailh hotswap sockets properly installed? They should be adhering to the cutout and should not have any balls of solder between the two bars.
3. Is your Pro Micro flashed? If not, go to the first question on the FAQ.
4. Are your switches properly installed? Reseat if needed.

## Do I need all the diodes?

It is recommended to put all the diodes in, even if you are doing the 18 key layout.

## The knob for the rotary encoder is really loose. Is it supposed to be like that?/ What screw do I use?

There is a tiny screw on the encoder which you need a T8 Torx or 2mm Allen key to fasten it. You can also put your own knob on if you have one.

## How do I get USB-C on my Duckboard?

In order to get a USB-C on the Duckboard, you’ll need to purchase a Pro Micro drop-in replacement that has USB-C separately. Some popular ones include Elite C’s, Nice!Nano’s, and BIT-C.

## My USB port broke! What should I do?

The USB port is probably the biggest shortcoming of the Pro Micro. If excessive force upwards is applied, it will easily break. To stop this, only lateral force should be applied, and you should take extra care when removing the cable. If yours has broken and you are an extremely proficient solderer, you can try desoldering the Pro Micro, resoldering the port, and soldering it back in. The likely better option is to desolder the Pro Micro, and order another one (or a USB-C replacement) and solder it onto the duckboard.

## There is so much flux residue on my board. Is there any way to clean it?

Using a static safe brush and some 99% isopropyl alcohol will easily clean that all off.

## Does the default hex work for both the 18 key and 21 key layouts?

Yes, remember to use the [hex for the R2](https://officialdoodboard.netlify.app/support/duckboard_R2_default.hex) layout from [dood’s website](https://doodboard.xyz/pages/support).

## I broke some/lost parts! What should I order?

* LED: SK6812 3545 Mini (Aliexpress may be your best bet :/)
* Diode: 1N4148 THT Diode
* Encoder: EC-11 Encoder
* OLED: The OlED is a .91” 128px x 32px OLED. Some may not work with the Duckboard, buy at your own risk.
* Hotswap sockets: Kailh hotswap sockets
* Screws: M2 Screws
* Nuts
* Standoffs