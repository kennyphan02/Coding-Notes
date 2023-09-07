
- CPU virtualization
	- Many virtal CPUs exist 
	- Time sharing: running one process, then stopping it and running another
		- Potential cost is performance
- A process is a running program
	- Process contains memory (contains instructions and data)
	- Process contains registers 
- Process API
	- Create - Creates a new process to run a program
	- Destroy - Destroys a process
	- Wait - wait for a process to stop running
	- Miscellaneous Control - suspend a process then resume it
	- Status - get info about a process

- How does the process creation works?
	- Loads a program code into memory and fills in an address space
	1. OS loads the process lazily (only essential pieces of code are loaded during program execution)
	- Eagerly means everything is loaded prior to program execution
	2.  The run time stack is allocated. This means is that after program execution the run time stack is used to store and handle variables (local variables, return address, function parameters). Every call performed in a thread stored in the stack 
			   To initalize the stack, call argc and argv array of main() function
	3. Heap is created 
		1. Heap memory is a type of dynamic memory allocation used for storing objects and data structures that require a longer lifespan than stack memory
		2. requests space by calling malloc() and free it by calling free()
	4. OS does other initalization tasks
		1. (input/ouput)
	Difference between heap memory and stack memory?
		Heap is used by all parts of an application and it is where objects are stored in. The stack memory contains the return address to it.