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
	- Formula: Tcompletion - Tarrival = Tturnaround
- Performance metric: Burst time
	- Burst time refers to the time required in miliseconds by a process for its execution. Also called execution time. (Changes from running state to completed state)
	- Burst time = completion time - waiting time 
- Performance metric: fairness
	- often at odds
- First in, First out (FIFO)
	- also known as FCFS (First come, first served)
	![[Pasted image 20230918134558.png]]
		The picture above is a ganatt chart. The average turnaround time is the sum of the turnaround time divided by the number of processes
	- FIFO is not that great when each process no longer runs for the same amount of time. see example below
	![[Pasted image 20230918135235.png]]
- Shortest Job First (SJF)
	- run shortest job first, then next shortest, and so on
	- non-preemptive scheduler 

- Pre-emptive vs nonemptive scheduling
	- Preemptive scheduling
	- When a process switches from running state to ready state or block/wait state to ready state. Resources are assigned to the process for a particular time and then removed. If the resources have remaining burst time, process is placed back into ready queue until it is given the chance to execute again 
	- A process can move from a running state to ready state if it needs to wait for a resource to become avaliable or due to priority issues when another process is assigned that has higher priority. 
	- Nonemptive scheduling
		- Processes in their ready state are queued waiting to be ran and executed. Processes are ran one at a time and hae to wait on each other. Ignores arrival time pretty much. Example of this is fcfs 
- Round Robin 
	- proccesses run for a fixed time 