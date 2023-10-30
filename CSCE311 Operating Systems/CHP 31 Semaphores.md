#### What is a semaphore?
an object with an integer value that we can manipulate using two routines:
- sem_wait()
- sem_post() (also known as signal())
```C
sem_t s;
sem_init(&s, 0, 1);
```
initalize the semaphore s, to 1 (passed in as the 3rd argument). The second argument, 0, means the semaphore is shared between threads in the same process.
Multiple calling threads may call sem_wait() and thus all be queued waiting to be woken. 
- sem_wait() decrements the semaphore while sem_post() increments it. 
- The value of the semaphore when negative is equal to the number of waiting threads. 
```C
int sem_wait(sem_t *s) {
	// decrements the value of semaphore s by one and waits if 
	// value of semaphore s is negative
}

int sem_post(sem_t *s) {
	// increments the value of semaphore s by one. if there are one or more
	// threads waiting, wake one up. 
}
```