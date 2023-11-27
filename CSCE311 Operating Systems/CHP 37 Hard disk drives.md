~~Understanding~~ some of the components of a modern disk 
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

### Seek Time

![[Pasted image 20231126230750.png]]
if we have multiple tracks, in order to access a given sector, the arm must have to move to the correct track. This process is known as ***seek***. After seeking, we wait for rotational delay. When the correct sector is under the head, the last stage is transferring. Data is either read/written from or written to the surface. 

4 stages of seek:
1. acceleration - arm gets moving
2. coasting - arm moving at full speed
3. deceleration - arm slows down
4. settling - head is carefully positioned over correct track. 

Multi-zoned disk drives - Disk is organized into multiple zones. A zone is a consecutive set of tracks on a surface. Outer trackers have more sectors than inner tracks because there is more room out there. 

### Track buffer
also known as a cache. Small amount of memory that the drive can use to hold data read from or writtten to the disk. 
1. Use case: An entire sector can be read from a track. The sectors would be stored in the cache. This allows the drive to quickly respond to any requests on the same track.


### Time vs Rate
-  T I/O Time = Tseek + Trotation + Ttransfer
- R I/O Rate = SizeTtransfer / T I/O Time

### Random Vs Sequential Access
Random workload - issues small reads to random locations on the disk
Sequential workload - reads a large number of sectors consecutively from the disk without jumping around

Sequential workload is typically faster for reading/writing data from a disk so SSDs are used. HDDs are used for storing large data. 

### Disk Scheduling
- The ***disk scheduler*** decides which I/O requests are scheduled next. Disk scheduler will try to follow ***Shortest Job First*** in its operation.
	- ***Shortest-seek-first*** - orderes the queue of I/O requests by track, picking requests on the nearest track to complete first. 
		- problem with SSF is the drive geometry is not avaliable to the host OS, rather it sees an array of blocks. 
		- another problem: ***starvation***. requests to other tracks would be ignored. 
			- Solution to starvation? ***SCAN*** - moves back and forth across the disk servicing requests in order across the trasks
		- Solution? implement ***nearest-block-first***. schedules request with the nearest block (sector) address next. 


### HDD vs SSD 
- Hard disk drives are cost-effective compared to SSDs for storing data. Hard disk drives generally can store more data than SSDs
- SSDs are faster for reading and writing data compared to hard disk drives 