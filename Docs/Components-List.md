
# Equipment
## Soldering Iron
A soldering Iron is ~~Helpful~~ Necessary. A solder sucker or solder wick is also necessary if you plan on rerouting the ports on the center board. Of course, you can avoid having to mod the board if you instead use a standard single board computer and a seperate display. I did not, however, because I overengineered the deck and only realized it after I bought and modded the display.

Soldering paste will also be helpful, as many of the components cannot be soldered without it.

## 3D Printer
This will be used to build the casing. However, Numerous other methods and materials can be used instead.

## Calipers
If you are using different components then the ones detailed in this documentation, then knowing their dimensions with sufficient precision is crucial to the design process.

## Another Computer
This will be used to write the firmware to both the Keyboard and the Raspberry Pi, design the PCB and case, and read this documentation.

# Keyboard
## Electrical Components
>[!TIP]
>To save on costs, see if your chosen supplier of components has a free sample request form. I applied for free samples to get the microcontroller for the keyboard, which saved me a decent chunk of money.

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
[FFC Cable](https://www.newark.com/multicomp-pro/mp-ffca05153052a/cable-assy-ffc-ffc-15-core-305mm/dp/83AH2530?ost=ffca05153052a)
[MicroUSB Port](https://in.element14.com/wurth-elektronik/629105150521/micro-usb-2-0-type-b-receptacle/dp/2470822#anchorTechnicalDOCS)
[Kailh Choc Tactile Switches](https://lowprokb.ca/collections/keyboards/products/sunset-tactile-choc-switches) (everywhere else was sold out, and I didnt want clicky or linear switches. I ended up having to settle for the clicky switches anyways, because I was not paying $9 for a pack of 10 switches.)

You will also need a special HDMI cable if you plan to attach a secondary display, as well as a USB to USB-C cable to power the display, and a USB to MicroUSB cable to connect the keyboard. both of these cables should be flexible enough to not interfere with the movement of the case.

## KeyCaps

If no modifications are made to the keyboard layout, you may have to make your own spacebars. This is due to the fact that the Footprint libraries I was able to find did not Include the Kailh v2 Switches, which have a different footprint than their previous versions. The unique stem of these keyswitches and the absence of keycaps larger than 2u wide impose additional restrictions, which are circumvented either by printing adapters that allow you to mount MX Style Keycaps, or by redesigning the PCB to use a different switch.

>[!NOTE]
>Turns out, [Chosfox](https://chosfox.com/collections/low-profile-keycaps) Sells 3U Kailh Choc v1 caps. This is great, since My project partner wasn't able to get 3D printed caps to work. As of this writing, the 3U caps only come in orange, but that may change by the time you are reading this.

Whatever you end up doing however, you will need a total of 72 Keycaps:
- 66x 1u caps (If desired, two of these should be Homing Keys)
- 4x 2u caps
- 2x 3u caps (These will need to be 3d printed, as they are not manufactured, apparently)

>[!WARNING]
>I forgot to make room for stabilizer bars on the pcb, so I'm using some foam to hold up the space bar. It's janky as hell, but at least that's on brand.

# Central Unit
This section includes anything attached to or powering the carrier board.
## Electronic Hardware
### Raspberry Pi 4 Compute Module
I was able to backorder a CM4 with 2GB of RAM for development. You'll want to spring for one with built-in Wi-Fi. I chose to forgo any internal eEMC storage, as 1) I wanted to be cost-efficient, and 2) I wanted to be able to easily swap out the Operating System for easy Development. However, It is entirely your choice whether or not to opt for eEMC.

### Waveshare 5" Touchscreen Expansion for Raspberry Pi CM4
The Cyberdeck Cafe recommends that your main display have a resolution that is at least 1024x600. however, I did not want this deck to be too much bigger than it already was, So I opted to allow for the optional addition of a second display, which could let the first display be used as a trackpad/status indicator/second display.

#### Disassembly of the Board

One downside to choosing this particular board is that it is very tall, so extensive modding is needed to prevent the keyboard from being at a height that would give you carpal tunel.

You will need to desolder the USB ports, the Fan Header, and the Ethernet port. GPIO can optionally be relocated, and so can the indicator LEDs. Note that the ethernet port on this board has four extra pins; Likely because the port has a transformer inside of it.

To access the backside of the board, you will need to foam and adhesive. Removing the foam is possible with a wiresaw, or even a hobby knife, but you run the risk of damaging the ribbon connectors if you don't disconnect the display first. To do so, first release the ribbon cables from their connectors. Then, use a spudger to carefully pry the metal tabs off of the side of the display. This will first release the capacitive touch screen; the next set of tabs underneath will release the display. At this point you can get rid of the foam, and reassemble the display while it is still disconnected, to prevent any dust from settling inside.

If you so desire, a custom breakout board could also be developed, and the screen could be replaced with a trackpad, e-Ink display, or realy anything you want.

>[!IMPORTANT]
>I had gotten so caught up in the designing of the thing that I forgot that** I could totaly just fit my regular Raspberry Pi somewhere else in the casing, and just use a less expensive display for this part**. Given the current shortages, it may be wise to use what you already have rather than break the bank on following my specifications exactly. It is for this reason that all the files in this repository are made to be easily modified, so you aren't forced to make my mistakes.

### Cat5e Cable
This is needed to modify the ethernet port on the carrier board. When soldered on, it should be no more than 6 inches in length. Some of the wires have to be twisted together, so make sure to figure out which ones those are.

### Other wires
These will be used to modify the rest of the board. I promise this section will get more specific in the future.

---

## Power
### CR1220 button cell Batery (x1)
This powers the RTC on the carrier board.

### RPi V3P UPS HAT (plus battery and power button)
The [RPi V3P UPS](https://www.makerfocus.com/products/raspberry-pi-expansion-board-ups-pack-standard-power-supply) from Makerfocus allows us to charge the battery while still using the deck, and is thus an optimal choice for powering the Pi and its carrier board. It also supports wiring an external power button (that lights up), which MakerFocus also sells. This board can be replaced with a number of alternatives though; one could maybe even use a regular charging bank made for cellphones, assuming the right voltage is provided. The casing was designed to be modified to your needs, and that includes makers on a budget.

### USB-C Panel-Mount Port
I chose to use [this model](https://www.adafruit.com/product/4218) from Adafruit since I did not feel like wiring a USB-C port to be flush with the case.

---

## Mechanical Hardware
### Neodymium Magnets
These are used in the Slide rails to lock the case open and closed, as well as in the side compartments to hold the covers on. Remember to adjust the size of the holes they get placed into so that your magnets will fit. I used 1mm diameter disc magnets with a depth of 1mm. You can buy these online.

### Metal Strips
These can (and probably should) be machined to better fit your needs. However, I had an Erector/Meccano set lying around, so I used the metal parts from that to make the various attachment points for the displays and rail system. you can find (suprisingly) accurate measurements for any existing Meccano components in their [patents index](https://www.meccanoindex.co.uk/Drawings/Parts.php?id=1675957997).

The particular metal strips I used had more than 11 holes. I only needed 11, but I only had strips that were either way shorter or way longer than I needed.

### Nuts and bolts
Speaking of that Erector/Meccano set, I chose to use the nuts and bolts from that set to secure the various case parts together. I am having trouble finding the specifications of those specific components, but they came in the 12-in-1 deluxe crane set. You can of course, alter the 3d model to use different parts, or even have the case snap fit together.

You will also need four M2.5 Screws, and some corresponding nuts. These nuts are typically hexagonal, with a thickness of 2mm a minimum width of 5mm. These will be used to mount the power board.

# Casing
You'll need a 3d Printer for this. Other manufacturing methods can be utilized if you don't have access to one. The entire casing can be printed in ABS, but you should be aware that ABS tends to warp as it cools.

Because I'm using ABS filament, friction-fit parts use tolerances of around ==0.5mm==. However, You should test what tolerances your printer and material works best with, and take into account the material's properties and quirks.

In addition to the 3D printed parts, we utilized some metal components from a Meccano/Erector set I had lying around, to add both stability and mounting points for additional components. It is for this reason that all the screws that *aren't* used for mounting HATs have a thread diameter of 3.6mm.


# Miscellaneous Peripherals
- (OPTIONAL) Small Mouse, USB Trackpad, or other pointing device
- MicroSD card (In the absence of any eEMC or M.2 SSD, the capacity of the microSD card will determine the avaliable storage space of the device. 32GB is usually a good starting point)
- A thin [HDMI Cable](https://www.amazon.com/NFHK-Degree-Right-Up-Multicopter-Photography/dp/B096K6MSCS) is needed if you plan on adding a secondary display.
- A USB soundcard like this [USB to audio jack adapter](https://thepihut.com/products/usb-audio-adapter-works-with-raspberry-pi). I incorporated this into my design as I wanted to have the ability to utilize audio.

---

Once you're done gathering all the things you'll need to make the NetRazr, continue to [[Create & Code the Keyboard|Step 2: Creating the Keyboard]].