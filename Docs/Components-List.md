# Equipment
## Soldering Iron
A soldering Iron is ~~Helpful~~ Necessary. A solder sucker or solder wick is also necessary if you plan on rerouting the ports on the center board.

## 3D Printer
This will be used to build the casing. However, Numerous other methods and materials can be used instead.

## Calipers
If you are using different components then the ones detailed in this documentation, then knowing their dimensions with sufficient precision is crucial to the design process.

## Another Computer
This will be used to write the firmware to both the Keyboard and the Raspberry Pi, design the PCB and case, and read this documentation.

# Keyboard
## Electrical Components

>[!WARNING]
>Because I used klepcbgen to make the pcb, I did not realize until too late that the components were extremely tiny. If you are a novice solderer, you WILL want to modify the board to use larger components. 

```csvtable
source: Schematics/netrazr_rev2/netrazr_rev2.csv
columns:
- Designator
- Package
- Designation
- Quantity
```
I found the Components in this list on these sites:
[22R Resistor](https://www.mouser.com/ProductDetail/Panasonic/ERA-6AHD220V?qs=sGAEpiMZZMtlubZbdhIBINE5Vwz7C5t%2F1COSCSmdUdY%3D)
[10kOhm Resistor](https://www.mouser.com/ProductDetail/Panasonic/ERA-6VEB1002V?qs=sGAEpiMZZMtlubZbdhIBIF3tu7NV9mhCMkhdtUityXk%3D)
[4.7uF Capacitor](https://www.mouser.com/ProductDetail/KYOCERA-AVX/08056D475MAT2A?qs=8gCCvWsAIP16fDHGJX3Haw%3D%3D)
[Crystal](https://www.mouser.com/ProductDetail/ECS/ECS-200-8-30-JGN-TR?qs=rQFj71Wb1eWMqX0Vmq2tsw%3D%3D)
[0.1uF Capacitor](https://www.mouser.com/ProductDetail/KYOCERA-AVX/08056D104KAT2A?qs=ZBeOGGPQgEFSiSMjaoxiBA%3D%3D)
[SPI header](https://www.mouser.com/ProductDetail/Amphenol-FCI/10129382-972002BLF?qs=0lQeLiL1qyb2YZ6YnOsbzg%3D%3D)
[22pF Capacitor](https://www.mouser.com/ProductDetail/KYOCERA-AVX/04026A220JAT2A?qs=k4kUdCzLgS4lZhgcMzX1uw%3D%3D)
[Diode](https://www.mouser.com/ProductDetail/Taiwan-Semiconductor/BZY55B12-RBG?qs=mAH9sUMRCtuMqULUHENO7w%3D%3D)
[FFC Connector](https://www.hirose.com/en/product/p/CL0586-0523-6-55#)
[MicroUSB Port](https://in.element14.com/wurth-elektronik/629105150521/micro-usb-2-0-type-b-receptacle/dp/2470822#anchorTechnicalDOCS)
[Kailh Choc Tactile Switches](https://lowprokb.ca/collections/keyboards/products/sunset-tactile-choc-switches) (everywhere else was sold out, and I didnt want clicky or linear switches)
## KeyCaps

If no modifications are made to the keyboard layout, you will have to make your own spacebars. This is due to the fact that the Footprint libraries I was able to find did not Include the Kailh v2 Switches, which have a different footprint than their previous versions. The unique stem of these keyswitches and the absence of keycaps larger than 2u wide impose additional restrictions, which are circumvented either by printing adapters that allow you to mount MX Style Keycaps, or by redesigning the PCB to use a different switch.

Whatever you end up doing however, you will need a total of 72 Keycaps:
- 66x 1u caps (If desired, two of these should be Homing Keys)
- 4x 2u caps
- 2x 3u caps (These will need to be 3d printed, as they are not manufactured, apparently)

>[!WARNING]
>I forgot to make room for stabilizer bars on the pcb, so I'm using some foam to hold up the space bar. It's janky as hell, but at least that's on brand.
## Hardware Components

>[!NOTE]
>Unfinished Section


# Central Unit
This section includes anything attached to or powering the carrier board.
## Electronic Hardware
### Raspberry Pi 4 Compute Module
I was able to backorder a CM4 with 2GB of RAM for development. You'll want to spring for one with built-in Wi-Fi. I chose to forgo any internal eEMC storage, as 1) I wanted to be cost-efficient, and 2) I wanted to be able to easily swap out the Operating System for easy Development. However, It is entirely your choice whether or not to opt for eEMC.

### Waveshare 5" Touchscreen Expansion for Raspberry Pi CM4
The Cyberdeck Cafe recommends that your main display have a resolution that is at least 1024x600. however, I did not want this deck to be too much bigger than it already was, So I opted to allow for the optional addition of a second display, which could let the first display be used as a trackpad/status indicator/second display.

If you so desire, a custom breakout board could also be developed, and the screen could be replaced with a trackpad, e-Ink display, or realy anything you want.

>[!IMPORTANT]
>I had gotten so caught up in the designing of the thing that I forgot that I could totaly just fit my regular Raspberry Pi somewhere else in the casing, and just use a less expensive display for this part. Given the current shortages, it may be wise to use what you already have rather than break the bank on following my specifications exactly. It is for this reason that all the files in this repository are made to be easily modified, so you aren't forced to make my mistakes.

---

## Power
### CR1220 button cell Batery (x1)
This powers the RTC on the carrier board.
### Pijuice UPS HAT
This will Power the Pi and its carrier board. This can be replaced with a number of alternatives; one could maybe even use a regular charging bank made for cellphones, assuming the right voltage is provided. The casing was designed to be modified to your needs, and that includes makers on a budget.

---

## Mechanical Hardware
### Neodymium Magnets
These are used in the Slide rails to lock the case open and closed, as well as in the side compartments to hold the covers on. Rememebr to adjust the size of the holes they get placed into so that your magnets will fit.

### Metal beams
These can (and probably should) be machined to better fit your needs. However, I had an Erector/Meccano set lying around, so I used the metal parts from that to make the various attachment points for the displays and rail system. I just hope the measurements work in my favor.

### Nuts and bolts
Speaking of that Erector/Meccano set, I chose to use the nuts and bolts from that set to secure the various case parts together. I am having trouble finding the specifications of those specific components, but they came in the 12-in-1 deluxe crane set. You can of course, alter the 3d model to use different parts, or even have the case snap fit together.

# Casing
You'll need a 3d Printer for this. Other manufacturing methods can be utilized if you don't have access to one. The entire casing can be printed in ABS, but you should be aware that ABS tends to warp as it cools.

Because I'm using ABS filament, friction-fit parts use tolerances of around ==0.5mm==. However, You should test what tolerances your printer and material works best with, and take into account the material's properties and quirks.

In addition to the 3D printed parts, we utilized some metal components from a Meccano/Erector set I had lying around, to add both stability and mounting points for additional components. It is for this reason that all the screws that aren't used for mounting HATs have a diameter of 3.6mm.

>[!NOTE]
>This is an unfinished section


# Miscellaneous Peripherals
- (OPTIONAL) Small Mouse, USB Trackpad, or other pointing device
- MicroSD card (In the absence of any eEMC or M.2 SSD, the capacity of the microSD card will determine the avaliable storage space of the device. 32GB is usually a good starting point)

---

Once you're done gathering all the things you'll need to make the NetRazr, continue to [[Create & Code the Keyboard|Step 2: Creating the Keyboard]].