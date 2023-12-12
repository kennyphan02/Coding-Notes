###  CPU virtualization
- Virtualizing many CPUs with physical CPU
- utilizes limited direct execution - runs program straight on cpu
- switching between processes utilizes a context switch
- includes registers 

### Memory virtualization
amount of data to be moved is large. 
- virtual addresses may be larger than physical address space on the machine


### External Fragmentation
Multiple holes of free spaces

### Internal Fragmentation
Allocator hands out chucks bigger than requested 

### Segmentation
technique that divides memory into different segments each with its own virtual address. represents different parts of a program such as data, stack, and heap. 
- Segmentation fault can occur when a program tries to access a memory location that is outside the bounds of its allocated segments. 
### CPU vs Memory Virtualization
- Memory virtualization easier than CPU


### Paging
get more ram by using a storage device such as a hard drive. 

### Page table
translates virtual address to physical address. translates virtual page number to physical frame number.