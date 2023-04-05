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
	- d2  = good suffix shift = d2(k) where k is the number of characters that match. to find the value of d2(k), use the pattern on itself until there is a mismatch 
		- Example: BAOBAB of K = 1. When k = 1, were looking at AB
		-          AB          AB        AB
		- BAOBAB  BAOBAB  BAOBAB     d2(1) = 2  = 2 shfits to the left 
	- d1 = bad suffix shift = t1(c) - k.  where c is the character's value found from the bad suffix table and k is the number of characters that match
		- After finding the character that is not preceded by the pattern, find the value of the character and plug it into c for t1(c)
		- N E W _ A B O U T
		- B A O B A B      here two characters (AB) match so K = 2. In our bad suffix shift table the character "_" = 6.  So D1 = t1( _ ) - K  = 6 - 2 = 4. 
	- Find the max of D1 and D2 and that is how much youre shifting the pattern by
		- D1 = 4 and D2 = 2   Max(D1,D2) = 4
	-

