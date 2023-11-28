### RAIDs
Redundant Array of Inexpensive disks - technique to utilize multiple disks to build a faster disk system.
- Looks like a disk and it is a group of blocks that can read/write RAID consists of multiple disks, memory, and 1 or more processors to manage the system 
- RAIDS are used for:
	- performance. using multiple disks in parallel can speed up I/O times 
	- capacity. more disks = more storage 
	- reliability. spreading data acrosss multiple disks makes the data vulernable to the loss of a single disk. RAIDs can tolerate the loss of a disk and keep operating as if nothing were wrong
- When a file system issues a I/O request to the RAID, the RAID must calculate which disks to use to complete the request and issue one or more physical I/Os, which depend on the ***RAID level*** 


### Approaches to building a RAID
Evaluate each RAID design along 3 axes
1. Capacity - given N disks and B sectors, how much useful capacity is avaliable to clients of the RAID
2. Reliability - how many disk faults can the given design tolerate?
3. Performance

3 Important RAID designs:
1. RAID level 0 (stripping)
2. RAID level 1 (mirroring)
3. RAID levels 4/5 (parity-based redundancy)

### RAID level 0: Striping
Serves as an upperbound on performance and capacity.  Helps optimize the speed of your hard drives. If one drive fails though, you will lose all of your data. 
- Striping improves performance by dividing data into sectors and writing those sectors simultaneously across multiple drives 
![[Pasted image 20231127213232.png]]
spread the blocks of the array across the disks in a round-robin fashion. We call the blocks in the same row a ***stripe*** 
![[Pasted image 20231127213605.png]]
Chunk sizes affect performance of the array. Small chunk size implies many files will get striped across many disks. Large chunk size reduces parallelism 
- Low latency (time it takes from data to transfer from one to another) due to utilizing multiple disks 
- disadvantages of raid 0 is that if one disk fails, all data in the is at risk. doesn't provide fault tolerance. 
- risk of data loss . 
- lack of redundancy 


### Raid level 1: Mirroring
- Making more than one copy of each block in the system. each copy should be placed on a separate disk. 