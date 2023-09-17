

Which of the following CPU scheduling algorithms are preemptive, as discussed in class? choose one 
FCFS 
HFCS 
SJF (a.k.a. SJN)
***STCF***


Given that CPU virtualization and Memory Virtualization both require hardware support to do 
efficiently, which of the following is a reason for Memory Virtualization to be more challenging? 

There are more registers for memory virtualization to be saved. 

***The volume of data stored in memory (RAM) is much higher than is part of the non-memory CPU state. (Backing up is impractical) ***

The volume of data stored in registers is much higher than is part of the memory (RAM) state. 

(Backing up registers is impractical) There are no registers for memory virtualization to be saved.


Which of the following are goals of memory virtualization? 
***Giving programs/programmers a simplified view of available memory.
Protecting one program (and the system in general) from a malfunctioning program. 
Efficiency**
Allowing, for certain scen*arios, relocating programs to different regions or just swapping program memory out to disk to free up memory.


  
The following issues are most likely to be experienced in a system that preallocates a standard size to a program, such as 512 MB exactly:

1. **Internal Fragmentation:** This is the primary issue that would be encountered when preallocating a fixed size to a program. Since the program is given a fixed, specific amount of memory (512 MB in this case), it may not utilize all of it efficiently, leading to internal fragmentation where some memory within the allocated block remains unused.
    
2. **Smaller programs may not be able to run as there is too much space between the stack and heap:** With a fixed allocation of 512 MB, smaller programs may find it challenging to fit within this large preallocated space, and there could be a significant gap between the stack and heap. This can lead to inefficient use of memory and may prevent smaller programs from running efficiently.
    

