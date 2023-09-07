Which of the following is an issue with separate threads or processes accessing the same piece of memory?


1.Programs cannot share memory
	2.*Separate machine instructions from separate threads/processes (e.g. load, add, store) can be interleaved and end up with rxandom results.*
3.Devices such as DRAM store values are volatile.
4.Provide high performance by minimizingthe overhead of the OS which must strive to provide virtualization without excessive overhead.

Which of the following best describes what CPU virtualization is.
Creating an environment where processes may pretend they have exclusive use of a RAM memory. Creating a fake CPU to park a running process on (stopping execution). 
Creating a real CPU to start a running process on (initiating execution). 
*Creating an environment where processes may pretend they have exclusive use of a CPU.*

Which of the following best describes what Memory virtualization is. 
*Creating an environment where processes may pretend they have exclusive use of a RAM memory.* Allowing a process to run over a network connection. 
Allowing a process to run directly from a hard drive without being loaded into RAM. Creating an environment where processes may pretend they have exclusive use of a CPU.

A process running on the CPU is in the _____________ state. 
Blocked 
Initial
Ready
*Running*

Why might a process enter the blocked state? choose the correct answer(s) listed below 
1. *It's waiting on data coming in over the network. 
2. *It's waiting on a file to be loaded. **
3. It's waiting on the stupid, slow human to type in their name. 
4. The CPU scheduler is trying to find a CPU for it.

  
Direct Execution is slower than Limited Direction Execution for a single job, which is why it is rarely used for multi-user systems. FALSE

Division by zero and system calls are alike becuase they (for a typical OS)... 
1. both cause the machine (hardware) to kill the process.
2. both cause the OS to be loaded.
3. *are both the same sort of error as far as the OS handler can tell.. *
4. are normally both be replaced by library calls.

Each process usually has a minimum of two stacks associated with it (or more possibly if multi-threaded). TRUE

A program is just a process loaded from some sort of storage (disk, etc.) that is setup to run on the CPU. FALSE


The OS often has multiple processes to schedule from a list of process that are ready to run on the CPU. What is probably stored in the queue, perhaps as pointers to the items?
1. **Process control blocks ****
2. The process registers
3. The start of the process address spaces 
4. Interrupt Descriptor Tables

