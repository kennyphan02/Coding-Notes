- Process - virtualization of CPU
- Address space - virtualization of memory 

### File
- a linear array of bytes. each file contains a low-level name. The low-level name of a file is often referred to as its ***inode number*** (i-number) 
### Directory
- like a file, also has an inode number but its contents are specific. contains a list of (user-readable name, low-level name) pairs.
	- For example, a file is named called "foo" but has the low-level name "10". The directory that this file reside in would have an entry of ("foo","10") that maps the user readable name to the low-level name. 
- Directories within directories is called a directory tree/hiearchy
	- The directroy hiearchy starts at a root directory. uses a separator (/) to name subdirectories

### INode
Inode is a persistent data structure kept by the file system that has information. all inodes reside on disk. copy of active ones are cached in memory. 


### Hard Links
removing a file is performed via unlink().
link() - takes 2 arguments. an old pathname and a new one. When you link a new file name to an old one, you create another way to refer to the same file. `ln` is used to do this `ln` is hard link.  (Think of pointers). Both files refers to the same inode number 
- When creating a file two things happen. 
	- 1. You create the inode structure that tracks information about the file (size, where its located on the sectors)
	- 2. Linking a human-readable name to that file and putting that link into a directory 
- After creating a hard link to a file, the file system perceives no difference between the original file name (file) and the newly created file name (file2)
![[Pasted image 20231128161747.png]]
This works b/c when the file system unlinks file, it checks the reference count within the inode number. This allows the file system to check to see how many times the inode number is referenced. When unlink() is called it removes the link between the human-readable name to the given inode number and decrements the reference count. 