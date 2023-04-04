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
- Shifts the position based off the first character's mismatch using its character's value
- 10 comparisons
- ![[Pasted image 20230404181938.png]]


Good-suffix shift
- Applied after 0  < k < m characters were matched
- d2(k) = distance between matched suffix of size k and its rightmost occurence in the pattern that is not preceded by the same character as the suffix  
- d2k = good suffix shift
- d1 = bad suffix shift 