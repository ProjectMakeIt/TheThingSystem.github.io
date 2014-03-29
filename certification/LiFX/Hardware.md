===Hardware

When operating the bulb temperature is approximately 21F (70).

Locate a the metal spring visible between the body and the diffuser of the bulb. Push the metal spring down—towards the base of the bulb—with a small screw driver. Turn the diffuser clockwise, lift the diffuser off.

This exposes the PCB holding the LEDs. Unscrew and detach the board, the continue and unscrew the the two screws holding the plastic hatch in place. Lift the hach off. The controller card is attached to the hatch. Unplug the connector and remove the board and hatch. Bend the hatch to enable you to lift the clear back of the hatch free. The networking board is visible.

The power board is in the stem of the bulb and encased seperately in silicone sealant.

There are two main ICs on the networking/controller board. These are at TI CC2538xFnn—this is an ARM Cortex M3 SoC which also handles the 2.4GHz Zigbee mesh between the LiFX bulbs—and another chip custom branded LIFX LWM-01-A. This second IC is a BGA chip, with its own crystal. Both the Lifx chip and the TI chip have their own 10-pin header block nearby (presumably a JTAG header for debugging?). However since the TI chip is 802.15.4 only you have to presume that this is the chip that handles 802.11 (i.e. Wi-Fi) for the LiFX bulb.

===Notes

Unlike some other bulbs, the LiFX is designed to be non-destructively taken apart. The diffuser can be pried off (with care) and the LED and networking/control boards can be removed and reattached. The networking/control board also has two 10-pin header block which could be used for debugging or reprogramming. The power board is not designedto be removed and—like the Philips Hue—is encased in Silicone.

The bulb is much heavier than many other of the competing bulbs, presumably due to the way it has been designed to be taken apart, and it's heavy enough so that you probably can't use it in a lightweight angle-poise lamp.

Unlike some of the other bulbs such as the Philips Hue—and despite the weight of the bulb—the diffuser on the LiFX bulb is made of plastic. You would expect this to adversely affect the quailty of the light from the bulb.

===FCC

The FCC Exhibits List is at https://apps.fcc.gov/oetcf/eas/reports/ViewExhibitReport.cfm?mode=Exhibits&RequestTimeout=500&calledFromFrame=N&application_id=216608&fcc_id=2AA53-LIFX01. Found this via a link, as I can't get the FCC search engine to work.

===Pictures

00		The LiFX box

01		The LiFX bulb

01a		The bulb in a lamp fixture after 30min (in C)

01b		The bulb in a lamp fixture after 30min (in F)

02		The bulb with diffuser removed

03		Close up of the LED PCB in place

04		LED removed from bulb

04a		LED removed from bulb (being held)

05		Macro of the LED PCB

06		LED PCB next to bulb

07		Hatch opened on the bulb

08		Hatch (and associated controller/networking card) removed

09		Hatch (and associated controller/networking card) before dissaembly

10		Back removed from hatch

11		Hatch disassembled

12		Controller/networking card

13		Controller/networking card with silicone cover removed (reset switch on right)

14		Close up of controller/networking card

14a		Close up of controller/networking card (alternative view)

15		Macro of LIFX LWM-01-A chip

16		Macro of TI CC2538 chip

17		Stem and Head of bulb detached

18		Stem of bulb

19		Stem of bulb end on (being held)

20		Power board incased inside silicone and inside stem

21		Power board incased inside silicone and inside stem (being held)

22		Power board incased inside silicone (plastic removed)

23		Power board

24		Power board (capacitor side, some silicone still evident)

25		Controller/networking board (left) and LED board (right)