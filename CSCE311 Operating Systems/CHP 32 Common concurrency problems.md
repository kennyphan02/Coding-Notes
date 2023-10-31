### Non-deadlock bugs
- Atomicity violation - when a code region is intended to be atomic, but the atomicity is not enforced during execution. 
	- One solution is to add a lock around the code 
- order violation
	- The desired order between two memory accesses is flipped (i.e A should always be executed before B but the order is not enforced during execution)
	- solution is to enforce ordering through using condition variables 

### Deadlock
- deadlock occurs when  thread 1 is holding a lock L1 and waiting for another one L2. Thread 2 however, holds L2 and is waiting for L1 to be released. 
4 Conditions for deadlock:
- mutual exclusion - prevents multiple threads from accessing a shared resource
- hold-and-wait - threads hold resources allocated to them (locks that they have already acquired) while waiting for other resources (locks that they wish to acquire)
- no preemption - resources can't be removed from threads that are holding them
- circular wait - circular