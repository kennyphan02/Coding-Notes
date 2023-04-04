- Construct a Bad Match Table
	- Value = length - index - 1 (Every other letter = length)
- Shift the position based off the value from the bad match table in the last comparison that finds  mismatch 
- Last character = length of pattern

Difference between Horspool Algorithm and Booyer-Moore algorithms
- Bad-symbol shift  shfits the position by the value from the bad match table 
- Horspool Algorithm shifts the position by the first value the pattern is being compared to if it finds a mismatch in the first comparison or the rest of the comparisons
Example of Horspool Algorithm
![[Pasted image 20230404181053.png]] 
- BARBER is shifted by 4 to the right because A's value = 4. there are 1 comparisons (R compared to A)
- BARBER is shifted by 1 to the right because E's value = 1. there are 1 comparisons (R compared to E)
- In the last shift, Barber is shifted by none as it finds the pattern. there are 6 comparisons (BARBER = BARBER)
- 17 comparisons

Booyer-Moore Algorithm
- Construct the bad symbol shift table 
	- Value = length - index - 1 (Every other letter = length)
- Construct Good-suffix shift table
	- ![[Pasted image 20230404191014.png]]
	- k = 1  = AB
	- k = 2 = BAB
	- k = 3 = OBAB
	- k = 4 = AOBAB
	- k = 5 = BAOBAB
	- d2 = good suffix shift = the number of shfits it take to find a pattern matching where the first character is not preceded

Good-suffix shift
- How to use good-suffix shift in pattern matching?
	- Construct bad symbol shift table. 
	- Construct good-suffix shift table 
	- Find K. K = the number of characters that match each other before finding a mismatch
	- d2(k) =  ?
- Applied after 0  < k < m characters were matched
- d2(k) = distance between matched suffix of size k and its rightmost occurence in the pattern that is not preceded by the same character as the suffix  
- d2k = good suffix shift
- d1 = bad suffix shift 
- d1 = T1(C) - K   where C is the constant and K is the number of characters that match
- T1(C) = mismatch
- max(D1,D2) = d