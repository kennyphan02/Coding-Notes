- Problem with the first simple file system was that performance was terrible. 
- Fast File System was invented. file system structures to be disk aware. 
- keep same interface to file system (same APIs including open, read, write) but change internal implementation
- Fast file system divides the disk into a group of cylinders. the group of cylinders are the central mechanism that FFS uses to improve performance.

### (De)fragmentation
- fragmentation is when files are spread out.
- defragmentation is organizing the files to be in continuous block, improving read and write speeds 
### Cylinders
a set of tracks on different platters of a hard drive that are the same distance from the center of the drive

![[Pasted image 20231129002602.png]]
groups of cylinders. By placing two files in a group, it will not result in long seeks. To use these groups to stores files and directories, FFS needs to be able place files and directories into a group and track all information about them. To track, FFS includes the inode, superblock, datablocks 
![[Pasted image 20231129002749.png]]
this is what FFS keeps within a single cylinder group.

- inode bitmaps and data bitmaps are a good way to manage free space and allocate it to a file

### How to Allocate files and directories
- Keep related stuff together. FFS decides what is related and keeps in the same group. FFS makes use of a few simple placement heuristics
- First is the placement of directories. 
	- find cylinder group with low # of directories and high # of free inodes. Put the directory data and inode in that group 
- For files:
	- makes sure to allocate data blocks of a file in the same group as the inode, preventing long seeks between inode and data
	- places all files that are in the same directory in the cylinder group of the directory they are in 
### FFS Policy
![[Pasted image 20231129135011.png]]
- To read this, each directory and file contains an inode. The root directory / has an inode
- We have four files, `a/c` `a/d` `a/e` and `b/f`. A directory represents one data block and a file represents two. 
- We rearrange it so that the nodes and data blocks are in the same group. Files in the same directory are one another (inodes). 

### Without FFS Policy
### Inode allocation
- Rather than using the picture above, we can spread the inodes among groups to prevent a group's inode table fills up quickly. 
![[Pasted image 20231129135520.png]]
we now have this. files a/c, a/d, and a/e span 3 groups with the ffs approach

### What does FFS do about large files?
a large file would fill an entire block group
- Locality - accessing instructions where addresses are one near another (Like FFS policy placing data blocks and inodes in the same group to maintain locality) 
- Utilizing the large-file exception, FFS spreads the data blocks from the file in chunks across groups
![[Pasted image 20231129141710.png]]
