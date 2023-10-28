
### Banker's Algorithm
![[Pasted image 20231028060512.png]]
A. to figure out the matrix need, subtract the max matrix from allocation matrix
B. to figure this out, we need to utilize the need matrix and take a look at our avaliable resources. We analyze the processes and figure out which processes require resources lower than the avaliable amount. 
- P0 can't be executed first because D needes 2 resource and we only have 1. 
- P1 is executed since we have the avaliable resources to execute P1. (A and B)
- When P1 is executed, we deallocate the resources needed and add it to avaliable (use the allocation matrix to add from not the need matrix)
	- Avaliable (1,2,0,1) to (2,2,1,2)