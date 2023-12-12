
### Banker's Algorithm
![[Pasted image 20231028060512.png]]
A. to figure out the matrix need, subtract the max matrix from allocation matrix
B. to figure this out, we need to utilize the need matrix and take a look at our avaliable resources. We analyze the processes and figure out which processes require resources lower than the avaliable amount. 
- P0 can't be executed first because D needes 2 resource and we only have 1. 
- P1 is executed since we have the avaliable resources to execute P1. (A and B)
- When P1 is executed, we deallocate the resources needed and add it to avaliable (use the allocation matrix to add from not the need matrix)
	- Avaliable (1,2,0,1) to (2,2,1,2)
![[Pasted image 20231211210808.png]]
Avaliable changes from (1,2,0,1) to (3,2,0,1) 


![[Pasted image 20231030001259.png]]
- Request for (0,2,0) by process 0 be granted? What we do is:
	- Means we need 2 more resources for B in P0, so it goes from (0,1,0) to (0,3,0). Then we change the need from (7,4,3) to (7,2,3). Then we change the avaliable from (2,3,0) to (2,1,0)




### Resource Allocation Chart
A set of vertices V and a set of edges E
![[Pasted image 20231029224632.png]]
- If a graph contains no cycles, there is no deadlock
- if a graph contains a cycle, 
	- if 1 instance per resource type, then deadlock
	- if several instances per resource type, possibility of deadlock
![[Pasted image 20231029231622.png]]
Cycle but no deadlock. How it works is that P1 requests an instance of a resource from R1 but there is none avaliable. We go to P2 next. P2 holds a resource and is not requesting any resource. Eventually, P2 is done and the resource gets deallocated for P1 to be used. We go back to P1 and P1 holds an instance of resource 1. Eventually, P1 gets done. we go to P3 and P3 requests an instance of a resource from R2 which there is 1 avaliable. P3 gets done and resource is deallocated. P4 is ran and gets done too.
Order of processes ran P2 -> P1 -> P3 -> P4

#### Methods for handling deadlocks
- Ensure system will never enter a deadlock state 
- Allow the system to enter a deadlock state and then recover (like kill process)
- Ignore the problem and pretend that deadlocks never occur in the system

### Different states
Safe state
	systems in safe state if in a sequence of process, for each process that requests a resource, it can be satisfied due to avaliable resources + resources held by the other processes (like bankers algorithm ensures this)
If a system is in a safe state -> no deadlocks
If a system is in an unsafe state -> possibility of deadlocks
Avoidance -> ensure a system will never enter an unsafe state
- Single instance of a resource type
	- use resource-allocation graph
- Multiple instances of a resource type
	- use bankers algorithm

### Different edges
claim edge - Process has an edge to a resource  that may request the resource
claim edge converts to request edge when a process requests a resource 
request edge converts to assignment edge when resource is allocated to process
when resource is released by process, assignment edge reconverts to a claim edge 

