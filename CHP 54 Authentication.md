Principal - Party asking for something.
- security-meaningful entities that can request access to resources, such as human uesrs or softwares system.
- Operating system services are commonly requested by system calls made by particular processes. associated with the calling process is the OS-controlled data structure that describes the process, so the operating system can check that data structure to determine the identity of the process. 


- process performing the request on behalf of a principal is often called an agent. 
- the request for access to some resource is known as the object of the access request. 
- any form of data created and managed by the operating system that keeps track of such access decisions for future reference is called a credential. 


### How to Authenticate Users?
- authenticating the identity of human beings has worked in 1 of 3 ways:
	- authentication based on:
		- what you know
			- I.E passwords.
			- a system does not need to know the password. Instead, it stores a hash of the password. Hash the claim and compare it to the stored hashed value. Benefits of this includes:
			- Can't reverse a hashing algorithm to figure out a password. 
			- ***Cryptographic hashes*** is a type of hashing algorithm that make it hard to use the hash to figure out what a password is. 
				- Hard to design though.
		- what you have
		- what you are

dictionary attack - guessing passwords that could be a list of a names, and words before trying random strings of characters.