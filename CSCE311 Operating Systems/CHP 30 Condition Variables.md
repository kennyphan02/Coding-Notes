To wait for a condition to become true, a thread can make use of a condition variable.
	Condition variables - explicit queue that threads can put themselves on and waits until a particular condition occurs.
pthread_cond_t c - declares c as a condition variable.
- Has two operations with it: wait() and signal()
		- wait() is executed when a thread wishes to put itself to sleep (releases the lock)
		- signal() is executed when a thread has changed something in the program and wants to wake a sleeping thread waiting on this condition