### LFS
when writing to disk, LFS buffers all updates in an in-memory segment. When the segment is full, it is written to disk in one long, sequential transfer to an unused part of the disk. This makes it better for write performance due to sequential transfers being faster than random transfers
- LFS used for better write performance from writing data blocks and inodes to disk sequentially. 


### How do we find inodes in LFS
- inode map. it is a structure that takes an inode number as input and produces the disk address of the most recent version of the inode. imap needs to be kept persistent which allows LFS to keep track of location of inodes across crashes. 

### Where should we put the imap?
we place the imap next to the data block and inode. 


### Checkpoint region
File system must have some fixed and known location on disk to begin a file lookup. The checkpoint region is a fixed place on the LFS that contains pointers to the inode map.  Inode map can be found by reading the CR first. 