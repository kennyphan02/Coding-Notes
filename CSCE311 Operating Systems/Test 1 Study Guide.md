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


- Paging
	- - A region of virtual memory
	- Paging splits address space into fixed units called a page (virtual memory)
	- Physical memory is split into page frames (physical memory)
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
		- to find pte, need to know the starting location of the pte
		- paging requires to perform one extra memory referenec 