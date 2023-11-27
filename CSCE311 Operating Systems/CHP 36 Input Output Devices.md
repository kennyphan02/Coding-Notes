
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




Firmware - software within a hardware device 