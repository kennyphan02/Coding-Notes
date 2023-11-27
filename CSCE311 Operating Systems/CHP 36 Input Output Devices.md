
### Canonical Devices
- Two components
	- Interface - allows the system software to control its operation. All devices have specified interfaces.
	- Internal structure - implementation 
- ![[Pasted image 20231126193409.png]]
- Status register - check current status of device
- Command register - tells device to perform a certain task
- Data register - sends data to the device or gets data from the device 

### Polling
OS Interaction with the device might look something like this:
```
While (STATUS == BUSY)
	; // wait until device is not busy 
Write data to DATA register
Write command to COMMAND register 
	(starts the device and executes the command) 
While (STATUS == BUSY) 
	; // wait until device is done with your request
```
- Four steps. 
1. Waits by reading the status register and checks to see if it is busy. this is called ***Polling*** the device. 
2. OS Sends data to data register
3. OS writes command to command register
4. OS waits again until device is done, polling it in a loop.
- Polling is inefficient due to the amount of cpu time used for waiting for the device to complete its activity


### How can we avoid the costs of polling? Interrupts
OS can issue a request and put the process to sleep and context switch to another task. When the device is finished, a hardware interrupt occurs causing the CPU to jump into the OS at a predetermined interrupt handler. 
	Handler is a piece of code that will finish the request and wake the process waiting for the I/O
- ***Interrupts*** are used to allow devices to signal when an event needs immediate attention. Interrupts allows for overlaps of computation and I/O

### Interrupts vs Polling when to use?
- If a device is fast, use polling. The cost of using an interrupts and switching from one process to another is rather expensive.
- If a device is slow, use interrupts. 
- If the speed of the device is not known, use a hybrid (Polls for a while and if device is not finished, interrupt)

### DMA 
When using programmed I/O (PIO) to transfer a large chunk of data to a device, CPU is utilized inefficiently. CPU spends too much time moving data to and from devices by hand. How can we offload this work and utilize the CPU more effectively?
***Direct Memory Access*** - a device within a system that can control transfers between devices and main memory without much CPU intervention. 
![[Pasted image 20231126210035.png]]
To transfer data to the device (marked as c), the OS programs the DMA to do this feat by telling where the data is in memory and how much data to copy and which device to send it to. 
***Our goal is to copy data from memory and transfer it to the disk***. By utilizing a DMA, it free's up the CPU's work on having to copy data from memory and can move on to working on another process. 


### How does the OS communicate with the device?
Two primary methods of device communication
1. Explicit I/O instructions 
	- These instructions specify a way for the OS to send data to specific data registers. (I.e, using in and out instructions on x86). for example, to send data to a device, caller specifies a register with the data in it, and a port which names the device. These instructions are ***privileged***.



Firmware - software within a hardware device 