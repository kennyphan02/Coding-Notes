
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
