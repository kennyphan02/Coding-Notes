
### Locks
Providing mutual exclusion to a critical section can be obtained via locks. Basically means providing protection for a critical section so that code doesn't get interrupted. 
	Mutual exclusion means blocking multiple threads from accessing the same data. 
```
pthread_mutex_t lock; 
pthread_mutex_lock(&lock);
x = x + 1; // or whatever your critical section is 
pthread_mutex_unlock(&lock);
```
If no other thread holds the lock when pthred_mutex_lock is called, the thread will acquire the lock and enter the critical section. If another thread holds the lock, the thread trying to grab the lock will not return from the call until it has acquired the lock.
This lock is not initalized. To initalize it, use `pthread_mutex_t lock =  PTHREAD_MUTEX_INITALIZER`. sets the locks to default values. Dynamic approach is: `int rc = pthread_mutex_init(&lock, NULL)` and then `ASSERT(rc == 0)`
This block of code doesn't check for error codes so failures could happen causing multiple threads to enter a critical section. 
