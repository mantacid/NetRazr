When developing this project, I made the mistake of designing the case first. It ended up working out, but it was a lot harder to keep redoing the case than it would have been to save that part for last.

You can find all 3d models used in this project in the `Models` Folder. I apologize for the fact that they are blend files, It was what I had experience with, and it allowed me to make the model easily modifiable.

>[!WARNING]
>For some reason, blender decided that none of the faces of the model would be at right angles with eachother, so you may notice some oddities in the model. While I couldn't fix it completely, I made sure that any deviation was within 0.1mm. I wil attempt to rectify this issue fully in future commits.

# Modeling the Case
## The Shell
The case will have two halves -- one for each half of the split keyboard -- and those halves need to be properly scaled. Because I'm an idiot, I decided to use blender for this. Blender, while amazingly versatile, lacks some workflows needed to easily achieve the precision needed for fabrication.

Whatever software you decide to use, you'll probably have an easier time designing the case if you have a 3d model of the assembled PCB. To get this, export the KiCAD PCB as a STEP file, then ~~import it into OpenSCAD~~ Upload it to [ImageToSTL](https://imagetostl.com/convert/file/step/to/stl) and then import it into whatever CAD program you're using. I found that the model got scaled up by a factor of 1000 upon import, so I used some measurements I made in KiCAD to resize the model appropriately.

Each half of the case will be composed of three peices: the bottom (which holds the rails and carrier board), the top half (holds the keyboard), and the friction-fit bars that hold the keyboard PCB in place and that definitely isn't there because I thought the PCB could slide in place after the switches were added. Additionally, there are also some 3d printable rail components that slot into the bottom halves, contain slots for magnets, and are secured with some Erector set components.

Aside from the third part, both halves are held in place with identical bolts, threaded through embedded nuts adhered to the case.

Should you have a different carrier board (or a seperate SBC and a display) I have added vertex groups to each part of the casing that allow you to resize it with minimal effort.

### Design Considerations
When conceptualizing the design, we knew what features we wanted to include, and thus needed to design the casing accordingly.

- Attachment point for secondary display
- Method for replacing Port Panels
- Easy Dissassembly
- Some extra space for modifications and further development
- Compartments for Batteries and/or device storage

>[!NOTE]
>This section is a WIP.

### Material
My version of the casing uses ABS filament, since it was cheap and wouldn't soften easily. I was worried about ABS's tendency to warp, so I designed the case such that any warping would be limited to the bottom faces of the compartments.

### Further Resources:
Designing a mechanism by which one can easily disassemble the shell is a tough challenge. We want the casing to be durable, so 3D printing the threading for some screws was out of the question, as was a snap-fit connection due to the limited size of our print bed.

We chose to use an embedded nut to attach the casing, providing a durable thread where any failure is more likely to be at a point that can be easily repaired, and woundn't necessitate reprinting the entire case. Plus, I had an old Meccano set lying around, so I could borrow the nuts and screws from there, and wouldn't have to go to a hardware store.

There are other options avaliable, and you may find them to be more effective for your circumstances.
- [Threaded Connections](https://www.hubs.com/knowledge-base/how-assemble-3d-printed-parts-threaded-fasteners/)
- [Snap-fit Connections](https://www.hubs.com/knowledge-base/how-design-snap-fit-joints-3d-printing/)
## The Rail System
At first, I was planning to attach metal drawer rails to allow the case halves to slide apart smoothly. But because ~~I'm cheap~~ other parts of the project are requiring more effort than anticipated, I have decided instead to make a custom 3D-Printed rail system, that incorporates magnets that can keep the case open or closed. 

The blend files should include a backup with the rail objects seperate from the casing (using boolean modifiers to model the geometry), for easy modification and repositioning.

This rail system will also utilize some Meccano components for stability. You can find the original patent diagrams on [Meccano Index](https://www.meccanoindex.co.uk/Drawings/Parts.php?id=1675957997) for exact measurements (yes, the design really hasn't changed at all since 1930).
