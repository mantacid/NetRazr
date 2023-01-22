When developing this project, I made the mistake of designing the case first. It ended up working out, but it was a lot harder to keep redoing the case than it would have been to save that part for last.

you can find all 3d models used in this project in the `Models` Folder

# Modeling the Case

## The Shell
The case will have two halves -- one for each half of the split keyboard -- and those halves need to be properly scaled. Because I'm an idiot, I decided to use blender for this. Blender, while amazingly versatile, lacks some workflows needed to easily achieve the precision needed for fabrication.

Whatever software you decide to use, you'll probably have an easier time designing the case if you have a 3d model of the assembled PCB. To get this, export the KiCAD PCB as a STEP file, then ~~import it into OpenSCAD~~ Upload it to [ImageToSTL](https://imagetostl.com/convert/file/step/to/stl) and then import it into whatever CAD program you're using. I found that the model got scaled up by a factor of 1000 upon import, so I used some measurements I made in KiCAD to resize the model appropriately.

>[!NOTE]
>This section is a WIP.

## The Backplate / Integrated Heat Sink
WIP