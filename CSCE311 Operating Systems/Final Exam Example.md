1. Consider a 64 bit architecture machine where physical memory is 128 GB
	A. if we would like to run processes as big as 512 GB how many bits would be required for the logical address?
	- 1 KB = 2^10 Bytes
	- 1 MB = 2^20 Bytes
	- 1 GB = 2^30 bytes
	- 1 TB =2^40 Bytes
	- 512 GB =  2^9  *  2^30 = 39 bits 
		B. if we are using page sizes of 8 KB, how many bits are needed for displacement into a page?
		- 2^10 * 2^3 = 2^13  = 13 bits = offset
		- ![[Pasted image 20231212165112.png]]
		- C. if a single level page table is used, what is the max # number of entries? 26 
	- What is the size of this single level page table in terms of 8KB pages?
	- 2^7 times 2^30 since physical memory is 128gb = 2^37 -  (2^10*2^3) = 37 -13 = 24
 