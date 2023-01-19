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
	- Omega Notation (Ω) 
	- Theta Notation (Θ) (Average case complexity)

- Time Complexity Examples
	```Java
	// What is the time complexity of this given code?
    int sum = 0
    int N = input
    for(int n = N; n > 0; n /= 2){
	    for(int i = 0; i < n; i++){
		    sum++;
	    }
    }
    // Don't assume that bec
// N = 10, 
//outer loop = 10, 5, 2, 1
/**when N = 10
1 outer iteration 10inner iterations 
2 outer iterations 5 inner iterations 5 inner iterations 
3 outer iterations 2 inner iterations
4 outer iterations 1 inner iterations
	inner loop = (N/2 + N/4 .... + 1 Iteration)
**/
	```
```
```
    