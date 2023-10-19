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
