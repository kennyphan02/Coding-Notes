
### Locks
- A lock is a variable that holds the state of the lock at any given time. Can be declared as `lock_t variable`.
- Locks are either ****avaliable (unlocked)**** and no thread holds the lock or ****acquired (locked)****
- One thread holds a lock and is in a critical section. 
- **lock()*** tries to acquire the lock. If the lock is avaliable, the thread will accquire the lock and the thread will be known as the ***owner***. 
	- If another thread tries to call the lock() on that same lock variable, it will not return. 
- ***unlock()*** . Unlocks the lock. If no other threads are waiting for the lock it will change to a free state; However, if other threads are waiting for the lock to be unlocked, The next thread will accquire the lock and enter the critical section. 
- *Important*: Threads are scheduled by the OS. We use locks to have some control of scheduling. 

### Pthread locks
- name that POSIX library uses for a lock is mutex as it is used to provide mutual exclusion between threads. (means once one thread is in the critical section other threads are prevented from entering the critical section)
-```
```
pthread_mutex_t lock = PTHREAD_MUTEX_INITIALIZER; 
Pthread_mutex_lock(&lock); // wrapper; exits on failure 
balance = balance + 1; 
Pthread_mutex_unlock(&lock);
```
- Passes the variable `lock` to lock and unlock. We can have multiple locks to protect different variables. This increases concurrency. 
- ***Coarse Grained Strategy*** - using one big lock any time when a critical section is accessed
- ***Fine Grained Approach*** - using multiple locks to protect different variables and allowing more threads to be in locked code at once

### More about locks
Basic criteria:
- mutual exclusion - multiple threads can't be entered in a critical section at the same time.
- fairness - does each thread contending for the lock get a fair shot at acquiring it once it's free? (balanced)
- performance

### Implementing a Spin Lock using a Test-and-Set
```C
int TestAndSet(int *old_ptr, int new) { 
	int old = *old_ptr; // fetch old value at old_ptr
	*old_ptr = new; // store ’new’ into old_ptr 
	return old; // return the old value 5 
	}

```
![[Pasted image 20231023190651.png]]
Initializing the lock. Lock's flag is equal to 0. When we call the lock() method, the thread calls testandset method. We keep the current flag value (which is 0) to an `int old` and set the current's flag value to 1. We return the old value of the flag so that we dont spin in the while loop. Thread atomatically sets the value to 1 within the testandset method. 
If another thread calls the lock, it will be spinning until the lock is released. Then this thread holds the lock. 
- By making both the test (of the old lock value) and set (of the new lock value) a single atomic operation, we ensure one thread acquires the lock.
- locks spin using CPU cycles until the lock becomes avaliable. 
- To work correctly on a single processor it requires a preemptive scheduler (one that will interrupt a thread via a timer, in order to run from a different thread) without preemption, spin locks don't make much sense on a single CPU, as a thread spinning on a CPU will never relinquish it. 

### Evaluating spin locks
- correctness - provides mutual exclusion
- fairness - doesn't provide fairness since a thread may be spinning forever
- performance - spin locks don't work well on a single cpu, but does on multiple cpus. 


	- Spin locks can be deemed inefficient. Imagine that a thread acquires a lock and it is in the critical section and gets interrupted. A second thread can try to acquire the lock but finds that it is held. it will forever spin and spin. A timer interrupt goes off where thread 0 is run again which releases the lock. How can we develop a lock that doesn't needlessly waste time spinning on the CPU?

### How do we prevent spinning on threads?
Give up the cpu to another thread. We call the yield() method which a thread can call to give up the CPU and let another thread run. 
- A thread can be in 1 of 3 states, (running, ready, or blocked). Yield is a system call that changes the state of a thread from running to ready. The thread ***deschedules*** itself. 

