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
- Making more than one copy of each block in the system. each copy should be placed on a separate disk, tolerating disk faults. 
![[Pasted image 20231127223725.png]]
- When reading a block from a mirrored array, RAID has a choice of reading from either copy. I.E reading 5 RAID chooses to read from disk 2 or 3. when writing a block, no choice exists. RAID must update both copies of the data to main reliability. 
- mirroring good for tolerating disk faults. but raid-1 is expensive due to having multiple copies. 
- same latency on a single disk. for single read request. disk write is different. requires 2 physical writes to complete before its due but in terms of latency its roughly the same as a single disk write since the 2 physical writes happen in parallel. The thing is that the write must wait for both physical writes to complete which makes performance worse. 
- RAID-1 Sequential Write and Sequential Read: N * S/2  N = number of disks and S = number of sectors

### Raid Level 4: Parity
redundancy - the ability to sustain multiple disk failures 
- parity based approach attempt to use less capacity.
- a parity block stores the redundant information for the stripes of blocks 
- Uses XOR. if there are even number of 1s in the bits, return 0. if there are odd number of 1s in the bits, return 1. 
-![[Pasted image 20231127224722.png]]
So P = 0 because 2 1 even bits = 0 
P in row 2 is equal to 1 because 1 1 bit = odd = 1. 
Lets say C2 column value is gone. We have 0,0,1,0. = 1 for C2
- Raid 4 can only tolerate 1 disk failure. if more than one disk is lost, there is simply no way to reconstruct lost data. 
- Raid 4 utilizes an extra disk 
- when writing big chunk of data to disk, raid-4 can do full-stripe write
- ***additive parity*** - computing the new value of parity block after overwriting a block. We read in all of the other data blocks in the stripe in parallel and xor it with the new block to get the new parity block. The problem with this technique is that it scales with the number of disks and thus in larger RAIDs require a higher number of reads to compute parity. 
- subtractive parity - flip the parity bit if a block gets overwrite with a new value thats different from the old value. 
- Raid 4 has small write problems (bottleneck on parity)

### Raid level 5: rotating parity
same as raid level 4 but parity rotates. across drives 
stripes the parity as well. 
![[Pasted image 20231127231830.png]]


### Mirroring vs paritying
Mirror duplicates data among hard drives so that if one disk fails, the other(s) can continue operating. paritying utilizes parity data to provide fault tolerance; however, it can only tolerate up to one disk fault.