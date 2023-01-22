# Equipment
## Soldering Iron
A soldering Iron is ~~Helpful~~ Necessary. A solder sucker or solder wick is also necessary if you plan on rerouting the ports on the center board.

## 3D Printer
This will be used to build the casing. However, Numerous other methods and materials can be used instead.

## Another Computer
This will be used to write the firmware to both the Keyboard and the Raspberry Pi, design the PCB and case, and read this documentation.

# Keyboard
## Electrical Components

```csvtable
source: Schematics/netrazr_rev2/netrazr_rev2.csv
columns:
- Designator
- Package
- Designation
- Quantity
- Supplier
```

## KeyCaps

If no modifications are made to the PCB, you will have to make your own spacebars. This is due to the fact that the Footprint libraries I was able to find did not Include the Kailh v2 Switches, which have a different footprint than their previous versions. The unique stem of these keyswitches and the absence of keycaps larger than 2u wide impose additional restrictions, which are circumvented either by printing adapters that allow you to mount MX Style Keycaps, or by redesigning the PCB to use a different switch.

Whatever you end up doing however, you will need a total of 72 Keycaps:
- 66x 1u caps (If desired, two of these should be Homing Keys)
- 4x 2u caps
- 2x 3u caps
## Hardware Components

>[!NOTE]
>Unfinished Section


# Central Unit

## Electronic Hardware
### Raspberry Pi 4 Compute Module
I was able to backorder a CM4 with 2GB of RAM for development. You'll want to spring for one with built-in Wi-Fi. I chose to forgo any internal eEMC storage, as 1) I wanted to be cost-efficient, and 2) I wanted to be able to easily swap out the Operating System for easy Development. However, It is entirely your choice whether or not to opt for eEMC.

### Waveshare 5" Touchscreen Expansion for Raspberry Pi CM4
The Cyberdeck Cafe recommends that your main display have a resolution that is at least 1024x600. however, I did not want this deck to be too much bigger than it already was, So I opted to allow for the optional addition of a second display, which could let the first display be used as a trackpad/status indicator/second display.

If you so desire, a custom breakout board could also be developed, and the screen could be replaced with a trackpad, e-Ink display, or realy anything you want. 

## Mechanical Hardware
### Metal Backplate
This probably should be Custom machined, but bullying a thermally conductive peice of metal into submission should also work if you have a low budget (I have not tried this). See this file for Details (link coming soon)

### Drawer Rails
These can be found in a lot of hardware stores. You'll want to avoid ones with magnets.
>[!note]
>Dimensions coming soon

# Casing
You'll need a 3d Printer for this. Other manufacturing methods can be utilized if you don't have access to one. The recommended material for each part will be listed in that part's section.

>[!NOTE]
>This is an unfinished section


# Miscellaneous Peripherals
- (OPTIONAL) Small Mouse, USB Trackpad, or other pointing device
- MicroSD card (In the absence of any eEMC or M.2 SSD, the capacity of the microSD card will determine the avaliable storage space of the device. 32GB is usually a good starting point)

Once you're done gathering all the things you'll need to make the NetRazr, continue to [[Create the Keyboard|Step 2: Creating the Keyboard]].