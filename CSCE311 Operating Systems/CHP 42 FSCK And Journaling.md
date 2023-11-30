File Systems contain files and directories and metadata to support abstraction from a file system. 

A major challenge faced by a file system is what to do when theres a power outage or system crash? updating a persistent data structure can be tricky.  

### FSCK (File System Checker)
- Crash consistency problem
	- Solution to this is FSCK
	- FSCK finds inconsistencies and repairs it. Such an approach cant fix all problems (when an inode points to garbage data (no data).) we need to make sure metadata is consistent 
	- FSCK is ran before filesystem is mounted (means fsck is executed during system's boot process )
	- FSCK checks if superblock is reasonable 
	- FSCK scans the inodes, indirect and direct blocks, to see which blocks are allocated. uses this knowledge to produce a correct allocation bitmap. 
	- FSCk checks each inode 
	- checks the link count for each inode
	- checks for duplicates (2 inodes pointing to same block )
	- Problem with FSCK: Too slow

### Journaling (write-ahead logging)
when updating the disk, before overwriting structures in a place, write down a little note describing what youre about to do. (write ahead) and its get logged. by doing this, if a crash takes place during the update, file system can check the journal and find the note and try again. 
- Journaling adds a bit of work during updates to reduce work required during recovery. 


### Metadata Journaling vs 

