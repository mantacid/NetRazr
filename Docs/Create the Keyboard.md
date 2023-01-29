
# Keyboards have Firmware?
The keyboard runs special QMK firmware that was custom written for the NetRazr's Unique layout. It uses a ten-row, 8-column matrix mapped to a 5-row, 16-column physical layout. I could have optimised the firmware to use an 8x9 matrix instead, but there are a few reasons why I didn't:

1. Having the matrix be half as wide and twice as tall as the physical layout made debugging, keymapping, and wiring much easier.
2. The 8 empty slots would allow new makers to add new keys without changing too much of the firmware.

The source I compiled my firmware from will be included in the `Firmware` Directory of this Repository.

My recommendation for modifying the firmware is that it should be done on a linux machine, as it comes with the necessary C Compiler by default. 

For instructions on compiling and flashing the firmware to the microcontroller, lists of keycodes and compatible microcontrollers, and many other helpful references, refer to the QMK Docs.

## But I don't know C!
Neither do I. But I found the process of modifying the firmware to be simple nonetheless. 
An easy way to streamline and simplify this process would be to use the many online resources for defining custom layouts and compiling custom firmware. The ones I used in creating the firmware will be listed below, along with a brief sumary of my process.

## Developing/Modifying Firmware
### Setup:
First, Install the QMK tools on your computer. You'll find instructions for various operating systems [here](https://docs.qmk.fm/#/newbs_getting_started). Development was done using Raspbian Linux.

Second, Download the contents of the `/Firmware` directory from this repository and move the folder to `~/qmk_firmware/keyboards`.

You'll also need to download KiCAD, as well as the [klepcbgen](https://github.com/jeroen94704/klepcbgen) script and any footprint libraries you may need (such as those containing any obscure keyswitches you may use). KiCAD 6 also has an issue with 3D model libraries not working properly. There are a number of fixes for this, none of which worked for me. I had to find, doenload, convert, position, and replace each Component's 3d Model by Hand. If you find an easier way to mass-update the libraries, please tell me.
### 1. Generate the Layout
Using [Keyboard Layout Editor](http://www.keyboard-layout-editor.com/), I was able to create a custom layout for the keyboard. Remember to add Legends before the next step.
### 2. Build the Layout File
Copy the raw data from the Keyboard Layout editor, and paste it into [This Converter](https://qmk.fm/converter/). The resulting JSON File will be used to define your key layout.

### 3. Upload to QMK Configurator
Go to [QMK Configurator](https://config.qmk.fm/#/checkerboards/quark_squared/LAYOUT_4_2x225u) and define the Keymap, Microcontroller pins, and Maintainer Information. Once you're done, compile the firmware and download either the hex file or the source.

### 4. Generate the PCB Design
remember the layout JSON file from earlier? move that into the working directory of klepcbgen, and run

```bash
python klepcbgen.py -o mykeyboard example_layout.json
```
Replacing `example_layout.json` with the name of your layout file. once that's done, take the newly created `mykeyboard` folder and move it to wherever you keep your KiCAD files.

### 5. Polishing up the Design
Klepcbgen is not perfect, you will need to update the footprints, and probably rewire things because of it. Follow the instructions on the tool's Github page to perform all the necessary actions.

Additionally, I found that I needed to adjust the size of the Mounting holes, as the screws I was using were 3.6mm in diameter.

### 6. Assembly
Once the Keyboard's Design is up to your standards, get the [[Components-List#Keyboard|components]], order the PCB, and assemble the Keyboard.

From here, follow the QMK documentation instructions on flashing Firmware. Make sure the Keyboard works properly before continuing to [[Fabricate the Case|Case Fabrication]].