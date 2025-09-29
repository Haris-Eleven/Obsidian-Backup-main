# Theory
1. VLAs not allowed in cpp
size of array should be known at 
compile time

```cpp
-> Calculation is done in higher precedence data type 
1 = INT
1.0 = Double
1LL = Long Long
-> Precedence order: 
	Double -> Float -> Long long -> Long -> Int -> char

INT : -1e9 to 1e9
LONG INT : -1e12 to 1e12
LONG LONG : -1e18 to 1e18
DOUBLE : -1e32 to 1e32

Overflow: Cycles back 
```
Precision Errors : Double has high range at the cost of precision 
# Logic/Approach 
1. Check condition of both possible & not possible 
2. Prefix/ Suffix sum
3. Binary Search 
4.  DP
5. Convert to Graph problem 
6. Difference Array ( Range Based Queries ) 
# Difference Array
1. Range based query in O(1)
2. Idea = Prefix Sum 
3. Firing Bullets in Opposite Direction 
# Recursion
In theory, **any problem** that can be solved iteratively can be solved recursively, because recursion and iteration are computationally equivalent (both are Turing complete).
> ***Functional vs Parametric***
 What's the base case ?
  If i knew the answer to a subproblem how will i build up to the full problem ?
  Stack Overflow 
  multiple *Recursion* Calls
# Binary Exponentiation
1. Classic example of ***Divide & Conquer***
2. Why need Binary Exponentiation 
	pow function uses double data type which has precision errors 
3. Large Exponentiation 
# Binary Multiply
# Greedy  
- local optimum leads to global optimum just make the best decision in the present assuming that it ll lead to overall best decision
- some other approaches that might not feel greedy but are greedy Updating some variables without thinking abt the past


