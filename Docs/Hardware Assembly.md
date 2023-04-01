The following steps should be performed in order:

## Keyboard
1. Solder the Surface Mount components to the keyboard halves.
2. Solder in the Through-hole components.
3. Apply legends to the keycaps.
4. Put the keycaps on the keyboard.
5. Flash the bootloader through the SPI pins if necessary. the atmega32u4 has the amtel dfu bootloader preflashed, so this step shouldn't be necessary unless you want to use a different bootloader. 
6. Flash the firmware through the USB interface.
7. Once you've tested the Keyboard and are satisfied with how it works, you will need to desolder the pin header and the reset button, as they will get in the way when sliding the pcb into the case. The reset switch can be reattached if desired once the pcb is in the case.

## Display Board
1. Follow the [[Components-List#Disassembly of the Board|Board Disassembly]] Instructions.
2. Extend the ports & pins.
3. Extend the indicator LEDs, making sure to use long wires to make subsequent steps easier.
4. Reaffix the screen to the board.

## Case
1. 3D print the case parts.
2. Insert the embedded nuts, glue if necessary.
3. Glue in all the magnets. MAKE SURE THAT THEY ATTRACT BEFORE YOU GLUE THEM IN.
4. Slide the rails into the bottom halves of the case, then affix them with the screws through the metal strips. Make sure that the raised areas are close to the center of the case, and double check the alignment of the screw holes.

## Assembly
1. Attach the UPS board and audio card in their spots in the bottom case.
2. Route one of the USB port pairs to the smaller square hole in the left port plate.
3. Route the ethernet port to the larger square hole.
4. Route the GPIO to the long rectangular hole.
5. Insert the power button and the charging port into the right port plate.
6. Connect the power button to its port on the UPS board, and the charging port to the USB-C port.
7. Connect the antenna to the Compute Module.
8. Connect the compute module to the display board, adhereing the antenna to the nearest flat surface.
9. Adhere the display to the raised areas on the rails.
10. Connect the USB-C port on the display to one of the USB ports on the UPS.
11. Thread the indicator LEDs and the attached wires through the rectangular hole in the top-right case section. You will glue it in later.
12. Connect and position the battery.
13. Connect the audio card to the USB port pair that you didn't route to the outside of the case, and adhere that port to the inside of the bottom-left half of the case.
14. Plug a USB to MicroUSB cable to the same port pair. make usre it is adequately flexible, as it will connect to the keyboard.
15. Slide the keyboard halves into their respective halves of the top case parts, adding washers as needed to raise it well above the screen. Secure them with the small bars (these should friction fit, but can be adhered if needed). 
16. Align the mounting holes, and thread the Meccano bolts through them.
17. Connect the keyboard to the cable from step 14. 
18. Attach the two halves of each side together.
19. Place the side covers on.
20. Glue the indicator LED into the hole you threaded it through.