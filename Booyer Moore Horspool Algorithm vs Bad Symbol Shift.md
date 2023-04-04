- Construct a Bad Match Table
	- Value = length - index - 1 (Every other letter = length)
- Shift the position based off the value from the bad match table in the last comparison that finds  mismatch 

Difference between Horspool Algorithm and using a bad match 
- Bad-symbol shift  shfits the position by the value from the bad match table 
- Horspool Algorithm shifts the position by the first value the pattern is being compared to if it finds a mismatch.
Example of Horspool Algorithm
![[Pasted image 20230404181053.png]] 
- BARBER is shifted by 4 to the right because A's value = 4. there are 1 comparisons (R compared to A)
- BARBER is shifted by 1 to the right because E's value = 1. there are 1 comparisons (R compared to E)
- In the last shift, Barber is shifted by none as it finds the pattern. there are 6 comparisons (BARBER = BARBER)

Example of Bad Symbol Shift