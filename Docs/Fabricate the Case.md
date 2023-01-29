When developing this project, I made the mistake of designing the case first. It ended up working out, but it was a lot harder to keep redoing the case than it would have been to save that part for last.

you can find all 3d models used in this project in the `Models` Folder

# Modeling the Case
## The Shell
The case will have two halves -- one for each half of the split keyboard -- and those halves need to be properly scaled. Because I'm an idiot, I decided to use blender for this. Blender, while amazingly versatile, lacks some workflows needed to easily achieve the precision needed for fabrication.

Whatever software you decide to use, you'll probably have an easier time designing the case if you have a 3d model of the assembled PCB. To get this, export the KiCAD PCB as a STEP file, then ~~import it into OpenSCAD~~ Upload it to [ImageToSTL](https://imagetostl.com/convert/file/step/to/stl) and then import it into whatever CAD program you're using. I found that the model got scaled up by a factor of 1000 upon import, so I used some measurements I made in KiCAD to resize the model appropriately.

### Design Considerations
When conceptualizing the design, we knew what features we wanted to include, and thus needed to design the casing accordingly.

- Attachment point for secondary display
- Method for replacing Port Panels
- Easy Dissassembly
- Some extra space for modifications and further development
- Compartments for Batteries and/or device storage

>[!NOTE]
>This section is a WIP.

### Further Resources:
Designing a mechanism by which one can easily disassemble the shell is a tough challenge. We want the casing to be durable, so 3D printing the threading for some screws was out of the question, as was a snap-fit connection due to the limited size of our print bed.

We chose to use an embedded nut to attach the casing, providing a durable thread where any failure is more likely to be at a point that can be easily repaired, and woundn't necessitate reprinting the entire case. Plus, I had an old Meccano set lying around, so I could borrow the nuts and screws from there.

There are other options avaliable, and you may find them to be more effective for your circumstances.
- [Threaded Connections](https://www.hubs.com/knowledge-base/how-assemble-3d-printed-parts-threaded-fasteners/)
- [Snap-fit Connections](https://www.hubs.com/knowledge-base/how-design-snap-fit-joints-3d-printing/)
## The Backplate / Integrated Heat Sink
WIP