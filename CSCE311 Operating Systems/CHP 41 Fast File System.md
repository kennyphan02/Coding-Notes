- Problem with the first simple file system was that performance was terrible. 
- Fast File System was invented. file system structures to be disk aware. 
- keep same interface to file system (same APIs including open, read, write) but change internal implementation
- Fast file system divides the disk into a group of cylinders. the group of cylinders are the central mechanism that FFS uses to improve performance.


### Cylinders
a set of tracks on different platters of a hard drive that are the same distance from the center of the drive

![[Pasted image 20231129002602.png]]
groups of cylinders. By placing two files in a group, it will not result in long seeks. To use these groups to stores files and directories, FFS needs to be able place files and directories into a group and track all information about them. To track, FFS includes the inode, superblock, datablocks 
![[Pasted image 20231129002749.png]]
this is what FFS keeps within a single cylinder group.