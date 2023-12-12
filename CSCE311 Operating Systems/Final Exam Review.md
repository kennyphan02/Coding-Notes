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

### CPU vs Memory Virtualization
- Memory virtualization easier than CPU


### Page table
translates virtual address to physical address. translates virtual page number to physical frame number.