# NetRazr

16x5 ortholinear split keyboard for use in the netrazr cyberdeck. It's a bare bones design, but leaves room for upgrades and customization. There's no backlighting currently, but there's code to support it if you want to add that (you'll also need to add backlight controls to the keymap, as they've been removed from the default keymap).

If I was smart, I would have adapted Zack Freedman's MiRage design, but I don't know circuit Python. So I used an FFC cable to connect the two halves.


Based off of the prime_O by [MxBlue](https://github.com/MxBlu)  
Hardware Supported: custom pcb coming soon, ATMega32u2  
Hardware Availability: GB

Make example for this keyboard (after setting up your build environment):

    make netrazr/netrazr_rev2:default

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).
