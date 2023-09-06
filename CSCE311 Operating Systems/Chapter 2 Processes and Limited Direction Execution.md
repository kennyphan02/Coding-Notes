
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
	2.  The run time stack is allocated. This means is that after program execution the run time stack is used to store and handle variables. Every call performed in a thread stored in the stack 