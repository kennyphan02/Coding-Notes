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
	- Formula: Tcompletion - Tarrival 
- Performance metric: fairness
	- often at odds
- First in, First out (FIFO)
	- also known as FCFS (First come, first served)
	![[Pasted image 20230918134558.png]]
		The picture above is a ganatt chart. The average turnaround time is the sum of the turnaround time divided by the number of processes
	- FIFO is not that great when each process no longer runs for the same amount of time. see example below
	![[Pasted image 20230918135235.png]]
- Shortest Job First
	- run shortest job first, then next shortest, and so on
	- non-preemptive scheduler 