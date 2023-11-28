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
Inode is a persistent data structure 