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
			- key chain - an encrypted file kept on your computer that stores paswords
		- what you have
			- something physical like a dongle (security tokens)
			- USB that contains a hardware token can be plugged into a computer and the O.S will determine if the user trying to login has the proper device. 
			- One downside of this design is that if the device doesn't have frequent changes, a user can know the security token to access the device. (turns from what you have to what you know)
		- what you are
		- facial recognition (problems cause of lighting, )
		- biometrics - any implementation will have a false positive and false negative rate both are bad so you'd like both to be low. senstivity describes how close the match must be 

dictionary attack - guessing passwords that could be a list of a names, and words before trying random strings of characters.