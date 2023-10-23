
### Locks
- A lock is a variable that holds the state of the lock at any given time. Can be declared as `lock_t variable`.
- Locks are either ****avaliable (unlocked)**** and no thread holds the lock or ****acquired (locked)****
- One thread holds a lock and is in a critical section. 
- **lock()*** tries to acquire the lock. If the lock is avaliable, the thread will accquire the lock and the thread will be known as the ***owner***. 
	- If another thread tries to call the lock() on that same lock variable, it will not return. 
- ***unlock()*** . Unlocks the lock. If no other threads are waiting for the lock it will change to a free state; However, if other threads are waiting for the lock to be unlocked, The next thread will accquire the lock and enter the critical section. 
- *Important*: Threads are scheduled by the OS. We use locks to have some control of scheduling. 