- We can utilize a physical cpu and turn it into multiple virtual cpus through virtualization which allows multiple programs to run at the same time 
- Rather than thinking a single pc where instructions are being fetched and executed, a multi-threaded program has more than one point of execution
	- Each thread is like a separate process except that they share the same address space and can access the same data. 

### Threads
A single thread contains a program counter that tracks where the program is fetching instructions from. also contains its own private set of registers it uses for computation
	- If 2 threads are running on a single processor, when switching from one thread to another, a **context switch** must take place. Register state of thread 1 must be saved and register state of thread 2 restored before running thread 2. 
	- To store the states of the threads, a ***thread control block*** is needed to store the state of each thread of a process
	- Address space remains the same when we do a context switch 
	- Threads share the same address space and access the same data 
![[Pasted image 20231018194241.png]]
- The address space on the left represents a single thread process where it only contain one stack. The address space on the right represents a multi threaded process where theres 2 stacks. Any variables stored on the stack will be placed in a ***thread-local storage***, the stack of the relevant thread.
### Why Use Threads?
- Parallelism
	- Example: Incrementing each integer of a large array by one on a single-thread process is straightforward. iterate through the array one by one; However, utilizing multiple threads allows one to speed up the process of this by using multiple CPUs. This is called ***parallelization***. 
- Avoid blocking program progress due to slow I/O
	- Example: waiting to receive a message. Instead of waiting, by utilizing threads, a program can do something else like utilizing the CPU to perform computation. 


### More information about threads
- Given a sequence of instructions within two threads, there are different possibilities. For instance:
-![[Pasted image 20231020145057.png]]
Threads can be created and ran immeaditely after creation. Threads can wait until another thread is created before running. The ***OS scheduler*** is responsible for the order of thread creation. 
![[Pasted image 20231020175155.png]]
- This program counts *upwards* to 2,000,000 due to using 2 threads. Sometimes the program doesn't go all the way up to 2,000,000 and produces a counter of say, 1,987,354.
- ***Data race*** - results depend on the timing execution of the code. The result of the program above is inconsistent and is known as indeterminate. Multiple threads executing this code can cause a data race and this is known as a ***critical section***. 
- ***Critical Section*** - a piece of code that is shared that must not be concurrently executed by more than one thread. 
	- a piece of code that s
- Solution to fixing the issue of causing a data race: implement ***mutual exclusion***. If one thread is being executed within the critical section, prevent the other threads from running.
	- Atomicity
	- Solution: Synchronization primitives - hardware support + help from the OS will help us build multi-threaded code that accesses critical sections in a controlled manner. 