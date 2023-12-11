Operating systems can:
- rewrite any process's memory
- Read/write/delete/corrupt any files on any persistent storage
- halt execution of any process
- enable/disable device
- respond to any system call with a harmful lie
- it is impossible for a process to protect itself from a malicious operating system

### 3 Big security-related goals that are common to many systems, including operating systems
- Confidentiality - certain pieces of information should be kept hidden away from others. 
	- e.g in O.S, process's memory can't be read by another process
- Integrity - if Pieces of information/component of a system is supposed to be in a particular state, there shouldn't be something else that'll change it (e.g placing online order for delivery dont wan't malicious prankster to intercept your order and change it to 1000 orders)
	- basically data shouldn't be modifiable 
	- Authenticity is important as we want to make sure the piece of information/component is from a particular party. 
	- in O.S, for example, if a user writes to a file another user that doesn't have permissions to modify that file shouldn't have access to it. 
- Availability - if information is avaliable for your own or others' use, make sure an attacker cannot prevent its use. 
	- e.g in o.s, one process can't hog the entire CPU and prevent other processes from getting their share of the CPU.


### Designing Security Systems
1. Economy of Mechanism - keep system simple and small, easier to debug and understand behavior
2. Fail-safe defaults - Default to security. if policies determine behavior of a system, have the default for those policies be more secure
3. Complete mediation - For every action, analyze and make sure it meets security policies. 
4. Open design - assume attacker knows everything. design security from these ass
