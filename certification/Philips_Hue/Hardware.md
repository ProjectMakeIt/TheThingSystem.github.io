===Hardware

When operating the bulb temperature is approximately 79F (26C).

Removing the diffuser with a hacksaw you expose the PCB holding the LEDs—these are not RGB LEDS. Below that is a large Aluminium heat spreader, and the two separate circuit boards—one for power and one for networking encased back-to-back in silicone sealant.

The main ICs on the networking board, and the only ones of real interest, are the TI CC2530 SoC—which includes the 2.4GHx 802.15.4 for Zigbee, and n 8051 low-power micro-controller—along with a Macronix MX25L4006E—which handles the serial bus. 

===Notes

The Philips Hue bulb is solidly constructed, and not meant for to be disassembled.

The Philips Hue bridge is powered by an ST STM32F217VET6 ARM Cortex-M3 Chip, and also has a CC2530 along with a CC2590 (a RF Range Extender) chip.

===FCC

Foudn this copy of the FCC internals picture from the bridge, https://docs.google.com/a/bs4.nl/viewer?a=v&pid=sites&srcid=YnM0Lm5sfGJsb2d8Z3g6NWJiMDZkYjY3MmY5ZDQ1ZA, but can't make the FCC search engine return me anything directly. (Carl, this sounds like your line of work?)

===Pictures

00		Philips Hue box

01		Philips Hue bulb

01a		The bulb in a lamp fixture after 30min (in C)

01b		The bulb in a lamp fixture after 30min (in F)

02		The bulb with diffuser removed

03		The bulb with diffuser removed (being held)

04		The bulb with diffuser removed (plastic shield over LED PCB removed)

05		The bulb with diffuser and plastic shield removed (being held)

06		The bulb with LED board removed, showing the Aluminium heat spreader below

06a		Close up of the LED board

06b		Macro of the LED board

06c		Macro of the LED board

07		The bulb with the Aluminium heat spreader removed

08		The interior of the bulb, with the networking board (left) and power board (right) encased in silicone

09		The exterior Aluminium shielding torn back to expost the silicone encased boards

10		Aluminium and silicone removed to show the two boards back-to-back

11		The power board in-situ

12		The networking board in-situ

13		The power board in-situ (alternative view)

14		The networking board in-situ (alternative view)

15		The networking board

16		The networking board (back)

17		Macro of the CC2530 chip
	
18		Extreme macro of the CC2530 chip

19		Networking board (left) and LED board (right)
