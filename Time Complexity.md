# Time Complexity Notes

## Terrminology:

- **Basic Operation**: operation that contributes the most towards the running time of the algorithm

- **Time Efficiency:** determined by the number of repetitions of the basic operations of an algorithm as a function of input size (I.E O(N))

    - Indicates how fast an algorithm runs
    - number of basic operations an algorithm performs represented as a function of input size 

- **Space Efficiency** refers to the amount of space needed to allocate for an algorithm

- **T(n) = cₒₚC(n)**

    - T(n) is the running time

    - Cₒₚ is the execution time for basic operation

    - C(n) is the # of times basic operation is executed

    - n is the input size

    - Worst Case - Cwₒᵣₛₜ(n) - max # of times basic operation is executed over size n

    - Best Case: CBₑₛₜ(n) - min # of times basic operation is executed over size n

    - Avg Case: CAᵥg(n) - # of times basic operation is executed on typical input

        -Not average of worst and best case  

        -Exepected # of basic operations considered as a random variable under some assumption about the probabiity distribution of all possible inputs

- **Asymptotic Notations** - Mathematical notations used to describe the running time of an algorithm 
	- Big-O Notation (O-Notation) - worst-case complexity of an algorithm. Disregards constants
			- Big-O describes how the runtime of the algorithm grows as the input grows 
	- Omega Notation (Ω) 
	- Theta Notation (Θ) (Average case complexity)
	- 

- Time Complexity Examples
	```Java
	// What is the time complexity of this given code?
	int sum = 0; 
	for(int n = N; n > 0; n /= 2) {
		for(int i = 0; i < n; i++) {
			sum++;
		}
	}
	/**
	// Don't assume that because there is a nested for loop doesn't mean it will always run in O(N^2) time. Look at the basic operations. 
	When N = 10, 
	1 outer iterations = 10 inner iterations
	2 outer iterations = 5 inner iterations
	3 outer iterations = 2 inner interations
	4 outer iterations = 1 inner iterations
	We can conclude that the pattern is given an input size N, the number of iterations is halved in the innter loop. 
		N + N/2 + N/4 + ... + N/2^n  
		Simplified into N(1/2 + 1/4 + ... + 1/2^N)
		The pattern above displays a geometric series. Evaluating N(2) = 2N = O(N) as we get rid of constants when writing in Big O Notation
	**/
	
	```

