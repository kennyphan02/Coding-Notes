

Which of the following CPU scheduling algorithms are preemptive, as discussed in class? choose one 
FCFS 
HFCS 
SJF (a.k.a. SJN)  <--- apparently its this one
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
    

For a system using basic base and bounds registers (one pair per process), explain how an operating system may move/relocate a non-running process in memory.
Assume the bounds register is _size_ of the virtual address space (and not the last address in physical memory).

Select a large enough region of memory and change the bounds register in some sort of process structure (like a PCB).


  
In a system using a base and bounds register approach for memory management, the operating system needs to be involved in the following situations:

1. **When a process is starting (to find memory):** When a new process is created or started, the operating system is responsible for allocating memory for the process's address space. It needs to locate a suitable region of memory and set up the base and bounds registers for that process.
    
2. **When a process enters the ready queue, to set the base and bounds:** When a process is ready to run and is placed in the ready queue, the operating system may need to set up the base and bounds registers for that process if it hasn't already been done. This ensures that when the process is eventually scheduled to run, it can execute without memory-related issues.
    
3. **When a process is loaded onto the CPU, setting the base and bounds:** When the operating system schedules a process to run on the CPU, it must set the base and bounds registers to establish the correct memory boundaries for that process. This allows the process to execute within its allocated address space.
    
4. **When a process is blocked, waiting on I/O (e.g., saving the state of base and bounds somewhere):** When a process is blocked, it may be necessary for the operating system to save the state of the process, including its base and bounds registers, so that the process can be properly resumed when the I/O operation is complete.

(Memory Virtualization) Segmentation can be described constructively as Base and Bounds with more register pairs for different regions of memory (a.k.a. segments). true or false?

True.

Segmentation can indeed be described as a memory virtualization technique that is similar to Base and Bounds, but it uses more register pairs to manage different regions of memory known as segments. Each segment has its own base and bounds registers, allowing for greater flexibility in memory management by dividing the address space into multiple segments with different properties and access permissions. This approach enhances memory protection and allows for more efficient memory allocation and sharing compared to a single base and bounds pair used in basic memory virtualization.


Which are advantages of memory segmentation vs a simplier base and bounds approach? ***Segmentation reduces external fragmentation *****
Segmentation reduces internal fragmentation 
Segmentation is simpler 
Segmentation is faster


When a system uses Implicit Segmentation to identify the memory segment to access 
disables user mode 
uses the higher-order bits to select a segment 
disables kernel mode 
Uses the source (program counter, stack pointer, etc.) to determine which segment to access. 

Memory compaction is an attempt to reduce internal fragmentation true or false
FALSE

Memory compaction is a technique used to reduce internal fragmentation in a memory management system. It involves rearranging the allocated memory blocks to eliminate or reduce the gaps or holes between them, making it possible to use memory more efficiently and reduce wastage caused by internal fragmentation.

