bl### LFS
when writing to disk, LFS buffers all updates in an in-memory segment. When the segment is full, it is written to disk in one long, sequential transfer to an unused part of the disk. This makes it better for write performance due to sequential transfers being faster than random transfers. 
- LFS used for better write performance from writing data blocks and inodes to disk sequentially. 


### How do we find inodes in LFS
- inode map. it is a structure that takes an inode number as input and produces the disk address of the most recent version of the inode. imap needs to be kept persistent which allows LFS to keep track of location of inodes across crashes. 
- LFS inode map is used to locate the inode in an unsorted log

### Where should we put the imap?
we place the imap next to the data block and inode. 



### Checkpoint region
File system must have some fixed and known location on disk to begin a file lookup. The checkpoint region is a fixed place on the LFS that contains pointers to the inode map.  Inode map can be found by reading the CR first. 


### Garbage
LFS have garbage collection because it repeatedly writes the new version of a file to new locations on disk while keeping the old versions. LFS must periodically find these own dead versions of file data and inodes and clean them
Cleaning should thus make blocks on disk free again for use in subsequent writes. 
Garbage collection (frees unused memory for programs)
- LFS doesn't prevent fragmentation because of garbage collection.



- To ensure updating the checkpoint region happens atomically, LFS keeps two checkpoint regions, one at either ends of the disk, and writes to them alternately. this is so that when a crash happens, LFS can detect if the timestamp pairs are inconsistent. 
- FFS VS LCS
- FFS is good for read operations while LCS is good for write operaitons