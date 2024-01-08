Start with a simple model of computation (automata)
Inputs & Outputs of computers - strings
Def: An alphabet is any nonempty finite set for alphabet sigma. the elemnts of sigma are called symbols (also letter).


Ex: aabac.  5 symbols (count duplicates too). for any string x, use the absolute value of x to denote length.  So | aabac | = 5  

concatentiation is associative (xy)z = x(yz) = xyz

x^0 = empty string (epsilon)
x^1 = x
x^2 = xx
x^3 = xxx


Proofs by induction on string length.
Basic fact: for any string x, exactly one of the following holds: 
	1. x = empty string (epsilon) or unique 
	2. There exists a string y and symbol a such that x = ya
In case 2, length of y = length of x - 1 and y is called the principal prefix of x


Another use of induction: defining functions on strings: To define a function f on all strings:
1. Define f(epsilon) (base case)
2. Define f(x) for x=ya in terms of f(y) (inductive case)


Ex: length function
| epsilon | = 0
| ya | = |y| |x|   (any a = sigma)
Def: sigma star  denotes all strings over sigma
Ex: {0} star = {epsilon, 0, 00, 000, ..., 0^n}
Ex: {0,1} star = {epsilon, 0, 1, 00, 0,1, 10,11, ..} binary alphabet 