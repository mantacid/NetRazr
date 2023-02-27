This Documentation contains all the information you ned to build and/or modify the NetRazr Cyberdeck.

This documentation was designed to be read in the Obsidian Application, and as such some formatting may be broken when viewed on Github. I will try my best to make the two as compatible as possible.

![[Netrazr-Render-Test.png]]

# What is NetRazr?
The NetRazr is a [Cyberdeck](https://cyberdeck.cafe/mix/what-is-a-cyberdeck), designed to be unique, modifiable, and accessible to makers. It was planned, designed, and built on a budget, making implementation extremely flexible. Is the Compute Module/carrier board too expensive? Tweak the case and swap them out for a regular Pi and a screen. In this way, this documentation straddles the line between a parts list and loose hardware standard.

# Why'd you make it?
I thought it was cool, and I was tired of coming up with ideas and not being able to bring them into reality. So I showed the concept to a friend, and we both decided to make it a real thing.

---


# SPECS:
- Quad-Core ARM Processor
- Up to 8GB RAM
- Optional eEMC storage
- Real-time clock powered by a seperate button-cell battery
- Ports:
	- 3 USB 2.0 Ports
	- 1 USB-C Port (for power)
	- HDMI Output
	- Gigabit Ethernet
	- MicroSD Card socket
	- 40 Pin GPIO
	- PoE Header
	- Fan Header
	- M.2 Slot for Optional SSD
- Built-in 5" Capacitive touch display (800x480 px)
- Split Mechanical Keyboard with custom layout and firmware
- Ample space inside for modding
- 3D-Printed casing with optional wrist support

# How do I Start?
Every piece of information you'll need to make this device is included in this repository, and sorted into directories for ease of location. You are free to customize, modify, and/or improve these designs to better fit your use-case, so long as you attribute me.

## Making the NetRazr your own
When making this device, you may come up with ideas to make the system better suited for specific cases, or you may find ways to improve the deck overall. If you have made a significant change to how the deck functions, I encourage you to fork this repository and detail the implemented changes. Make sure to link back to my original repository, as well as to the one you forked from (if those two aren't the same repository).

To start building this project for yourself, Follow the checklist below (in order).
## Progress Tracker
The following sections detail the creation of the base system:
- [ ] [[Components-List|Aquire all Components]]
- [ ] [[Create & Code the Keyboard]]
- [ ] [[Fabricate the Case]] (IN PROGRESS)
- [ ] [[Hardware Assembly]] (IN PROGRESS)
- [ ] Firmware Setup

The following are just a few ideas for modifications that could be implemented:
- A secondary display placed in a more traditional location
- Internet over GSM
- Hot-swappable Linux images
- A mounting bracket to use your phone as a monitor over VNC
- Using AA batteries as a backup power source for off-the-grid applications