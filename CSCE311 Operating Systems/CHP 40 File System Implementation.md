
### How does the file system work?
Two aspects
- Data structures of the file system (what disk structures are utilized by the file system to organize its data and metadata)
- Access methods (how does it map the calls made by a process such as open, read, write onto its structures?) which structures are read during execution of a system call? which are written? how efficiently are all of these steps performed. 
- Has to track information of each file. (metadata)

### Very Simple File System (VSFS)
developing the on-disk organization of the data structures of the vsfs file system. We divide the disk into blocks. simple file systems use one block size
![[Pasted image 20231128200754.png]]
Data region - region of disk we will use for user data. 
We store this data in an inode which is a data structure. We need to reserve some space on the disks for the inode. We call this the inode table. inode table holds an array of on-disk inodes 
![[Pasted image 20231128201034.png]]
The file system listed above can store up to 64 files. (64 blocks)
- Our file system is incomplete. we need to find a way to track whether the inodes and data blocks are free or allocated. 
### Bitmaps
- A bitmap is use for the data region (data bitmap) and a bitmap for the inode table (inode bitmap). a bitmap is a structure where each bit is used to indiciate whether the block is free or in-use 
![[Pasted image 20231128201709.png]]

### Superblock
contains information about the file system such as how many inodes and data blocks are there.  The operating system reads the superblock to initalize the parameters. When files are accessed, the O.S knows where to look for in the data region/inode. 

### Inodes
Holds data from the files in a file system such as the size. Also known as index node. Holds metadata for a given file. inode is a low-level name of the file. 
