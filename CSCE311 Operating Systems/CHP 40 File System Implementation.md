
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

### Direct Pointers
important decision in the design of the inode is how it refers to where data blocks are. solution is have 1 or more direct pointers (disk addresses inside the inode). each pointer refers to each disk block that belongs to the file. limited by size of file 

### Indirect Pointers
to support bigger files, use these. instead of pointing to a disk block containing the file, it points to a block that contains more pointers which point to the file. An inode may contain multiple direct pointers and a single indirect pointer. if a file grows large enough, an indirect block is allocated
- ***Double indirect pointers*** if file size grows larger, a pointer that points to the indirect pointer that points to the direct pointers that point to the files. same for ***triple indirect pointer***. all of this is known as ***multilevel index***


### Creating, writing, reading file
When we create a file, we allocate an inode for that file. The file system will search through the bitmap for an inode that is free and allocate it to the file
- Reading a file
	- To locate the inode of the file, it must start from the root directory and traverse the way through the directory via inodes. Each directory has an inode. 
	- Finally once the inode of the file is read, it looks for the pointers pointing to the data blocks of the file. It uses these pointers to traverse through the directory to find the inode number of each directory and eventually finds the inode number of the file