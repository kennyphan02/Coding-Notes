Understanding some of the components of a modern disk 
### Basic Geometry
Platter - a circular hard surface where data is stored via inducing magnetic changes to it. A disk may have one or more platters. Platters are made with hard metal (like aluminum)
Spindle - Bounds the platters together. Spindle is connected to a motor that spins the platters around at a fixed rate. Rate of rotation is measured in RPM. Usually we are only interested in the time of a single rotation. 
Track - each platter contains a concentric circles of sectors. a concentric circle is a track. 
Reading and writing data involves using the disk head. There is one head per platter. Head is attached to an arm which moves across the platter to the desired track 
Sectors.
Cylinder - collection of all tracks that are the same distance

### Rotational Delay 
![[Pasted image 20231126224553.png]]
If our goal is to read sector 0. we wait for 0 to be rotated under the head. Currently, 6 is under the head. This happens in modern drives. we call this the rotational delay. worst case scenario is if we have to get sector 5. 