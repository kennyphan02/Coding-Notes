T(n) = aT(n/b) + f(n)
A = the number of splits
f(n) has to be the average case. f(n) is included in theta (n^d)
b = size of subproblems

T(n) = 3T(n/3) + n^2
A = 3 
b = 3
3 < 3^2 = 3 < 9  = O(n^2)

T(n) = 2T(n/2) + n
compare a to b^d 
2 = 2^1 = 2  which means O(nlogn)