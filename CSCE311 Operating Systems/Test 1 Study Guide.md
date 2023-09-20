Process Control Block - Stores the state of processes. 
- When a process is created, it is stored in memory as the new state.
	- New state - This is the state the process will be in while the process creation is taking place 
	- Ready state - After process creation is completed, the state is changed into the ready state. It is loaded into the main memory and will be placed in the queue of processes which are waiting for CPU allocation.
	- Running state - when CPU is allocated to the process the states changes to running 
**CPU Scheduling **
- Workload Assumptions
	- Each job runs for the same amount of time
	- All jobs arrive at the same time
	- all jobs use the CPU
	- run-time of each job is known
- Performance metric: Turnaround time
	- Formula: Texit - Tarrival = Tturnaround
	- find the average: just divide by the number of processes
- Performance metric: Burst time
	- Burst time refers to the time required in miliseconds by a process for its execution. Also called execution time. (Changes from running state to completed state)
	- Burst time = completion time - waiting time 
- Performance metric: fairness
	- often at odds

- Performance metric: Waiting time 
	- waiting time = turnaround time - burst time 
	- or waiting time = texit - tarrival - burst time 
- First in, First out (FIFO)
	- also known as FCFS (First come, first served). nonpreemptive
	![[Pasted image 20230918134558.png]]
		The picture above is a ganatt chart. The average turnaround time is the sum of the turnaround time divided by the number of processes
	- FIFO is not that great when each process no longer runs for the same amount of time. see example below
	![[Pasted image 20230918135235.png]]
- Shortest Job First (SJF)
	- run shortest job first, then next shortest, and so on
	- non-preemptive scheduler 
- Shortest time to completion (STFC)
		- pretty much adding preemptive to shortest job first. Preemptive refer to paper 
- Pre-emptive vs nonemptive scheduling
	- Preemptive scheduling
	- When a process switches from running state to ready state or block/wait state to ready state. Resources are assigned to the process for a particular time and then removed. If the resources have remaining burst time, process is placed back into ready queue until it is given the chance to execute again 
	- A process can move from a running state to ready state if it needs to wait for a resource to become avaliable or due to priority issues when another process is assigned that has higher priority. 
	- Nonemptive scheduling
		- Processes in their ready state are queued waiting to be ran and executed. Processes are ran one at a time and hae to wait on each other. Ignores arrival time pretty much. Example of this is fcfs 
- Round Robin 
	- proccesses run for a fixed time before moving on to the next process based on the quantum. 
- Priority Scheduling
	- 1. Low number = high priority
	- 2. preemptive


- # Paging
	- Paging allows a computer to simulate having more RAM than it actually does by utilizing hard disk space.
	- - A region of virtual memory
	- Paging splits address space into fixed units called a page (blocks of virtual memory)
	- Physical memory is split into page frames (blocks of physical memory)
	- Advantages of paging:
		- flexibility
		- simplicity - page in address space and page frame are same size. 
	- Two components in virtual address:
		- VPN: virtual page number
		- Offset: offset within the page 
	- Page tables can get large (32 bit address space)
		- stored in memory
		- page tables maps virtual page numbers (VPN) to physical frame numbers 
			- Page table is a data structure that maps virtual address to physical address with an array
		- pages: small sized chunks (powers of 2) of virtual address space. Each is gonna be stuck in a physical frame
	- Common flags of page table entry
		- valid bit - valid transition
			- protection bit - tells where page could be read from, written to, or executed from
			- present bit - tells if page is in physical memory or on disk
			- dirty bit - tells if page has been modified
			- reference bit - indiciates page has been acccessed 
	- Page table entry
		- entry in a page table that stores information about a page of memory. can contain information such as the different flags listed above. (protection, present, dirty, and reference)
		- to find pte, need to know the starting location of the pte
		- paging requires to perform one extra memory reference

- TLB/Page Table
	- ![[Pasted image 20230919160723.png]]
	- PFN - giant array of page numbers. goes by 8 bytes 

- Standard Convention for binary prefixes
	- 1 KB = 2^10 Bytes 
	- 1 MB = 2^20 Bytes
	- 1 GB = 2^30 Bytes
	- 1 Tb = 2^40 Bytes


- 1. Consider a 64-bit architecture machine where physical memory is 128GB. 
	- a. If we would like to run processes as big as 512GB how many bits would be required for the logical address? 
		- 1 GB = 2^30 bytes  512 = 2^9 bytes   =  2^39 bytes.  so 39 bits would be required
	- b. If we are using pages of size 8KB, how many bits are needed for displacement into a page?****
		- 1 KB = 2^10 bytes 8 = 2^3 bytes = 2^13 bytes this is the offset number for a virtual address.
	- c. If a single level page table is used, what is the maximum number of entries in this table?
		- We know 39 bits are required from answer A. and 13 bits is the offset number. That means the max number of entries would be 2^26 

- Page Replacement Table 
	- Page faults: count the amount of numbers that appear in the table
	- Page frame tables and reference string 
	- FIFO approach
		- Replace the one that has been in queue the longest.
	- OPT/MIN approach
		- Replace the page that will be referenced furthest in the future or not at all

- Paging example:
  ![[Pasted image 20230919224019.png]]
  - 15b virtual address = meaning that the size is 15 bytes (i.e 100 0110 0000 0000)
  - 5 bits for page directory for L1, 5 bits for L2, 5 bit offset
  - each page table entry is 8 bits. The the 1st bit on the farmost-left is the valid bit. If it is 1, go to the level 2 bit. If its 0, then dont. 
  5aa8 =  101 1010 1010 1000 .  this is split into 5 bits per vpn. it will end up as
     10110  10101  01000    L1 = 22  L2 = 21  offset = 8.   
     Start at L1. Look at page directory base register. Afterwards, starting from the end of the page count by increments of 2. PDBR = 57 in base 10. Go to page 57. Since L1 = 22, go to index 22 Count from 32 cause its a 32b page size. Shift twice to the leftand decrease the counter by 1. Keep doing it until u reach 22. answer is 0xA7. Convert 0xA7 to binary 
	     A7 = 10100111 = 1 | 0100111 = 39.  The high order bit is the valid bit and the 0100111 is the physical frame number.
	     We move on to level 2. We go to page 39. Since L2 = 21 B, start from the right and count to the left (32-21). Answer is 0xC9  =  1| 1001001 = valid bit = 73 base 10 
	     go to page 73 and use the offset number: 8. start from the left this time though. Start counting at 0 
  