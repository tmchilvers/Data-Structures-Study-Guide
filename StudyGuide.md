# Algorithm Analysis 
_Algorithm_ : A process or set of rules to be followed to solve a problem
	
## 1. Empirical (Experimental) Analysis
* Analysis performed by implementing two algorithms and run an experiment with the same input.
### Benefits
* Extremely accurate results (Actual runtime calculated)
### Disadvantages
* Not good for large data sets
* Cost efficient
* Difficult/lengthy to implement algorithms.
* Dependent on many variables (i.e. platform/hardware and compilers/linkers)

## 2. Mathematical/Asymptotic Analysis (Theoretical Analysis)
Analysis that determines factors that determine the run-time of algorithm
* input
* Quality of code
Run time depends on input (specifically the size)
* Algorithm can be defined as a function of the input
* Take into account all possible inputs
### Benefits
* Very cost efficient
* Not dependent on many variables (e.g. hardware, compiler, linker)
### Disadvantages
* Less accurate than empirical analysis

# Algorithm Run-times
1. 1 _Constant Run-Time_
* Programs with instructions executed only once, few at most.
2. log(N) _Logarithmic Run-Time_
* As N grows, programs slows down slightly. Takes input and is cut into series of smaller problems, cutting size by a constant at each step
2. N _Linear Run-Time_
* If N is a million, so is run-time.
3. Nlog(N)
* When N doubles, the run-time slightly more than doubles. Algorithms break problem into smaller problems, then combines results.
4. N<sup>2</sup> _Quadratic Run-Time_
* When N doubles, run-time increases by an order of 4.
5. N<sup>3</sup> _Cubic Run-Time_
* When N double, run-time(T(n)) increases by an order of 8.

# Big O Notation
Saying an algorithm is O(f(n)) is saying that in the the worst case, the run-time of the algorithm to be about f(n).
_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) <= c*g(n) for all n > n<sub>0</sub>_
### Little O Notation
_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) < c*g(n) for all n > n<sub>0</sub>_
### Big Omega Notation
_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) >= c*g(n) for all n > n<sub>0</sub>_
### Little Omega Notation
_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) > c*g(n) for all n > n<sub>0</sub>_
### Techniques for Analyzing Algorithms
* Just a few instructions, or numerous instructions that only execute once, f(n) is usually O(1).
* A problem that breaks n into smaller pieces at each step by a constant factor, f(n) is usually O(log n)
* A problem with a single loop iterating over n, then f(n) is often O(n)
* A problem where the big problem is broken into smaller pieces at each step, solved separately, and then combined, then f(n) is often O(nlogn)
* Double-nested loops iterating over n (all pairs), then f(n) is usually O(N^2)
* Triple nested loops O(N^3)
* A brute force solution that tries every possible combination of data to find a solution, then f(n) is often exponential


# Arrays  
An array is a collection of individual data values with two distingishing characteristics:
Any array ordered. You must be able to count off the values: here is the first, here is the second, and so on.
An array is homogeneous. Every value in the array must have the same type.
## Arrays as data structures 
* As with any other variable, arrays must be declared before you use them. In C++, the most common syntax for declaring an array variable looks like this:
 
```cpp
Type name[size];
```
 
Where _type_ is the element type, _name_ is the array name, and _size_ is an integer representing the number of elements.
 
EX. Int intArray[10];

### Benefits 
### Disadvantages 
### How to create/initialize an array 
### How does an array differ from other data structures (i.e. Linked Lists, Trees)  
## Big-O Runtime 
### Access 
### Insert 
### Search 
### Delete 

# Linked List/ Double Linked List  
###Benefits  
Disadvantages  
How to create/initialize an array  
How does a list differ from other data structures (i.e. arrays, Trees)  
Big-O Runtime 
o Access 
o Insert 
o Search 
o Delete 
Abstract Data Structures (ADT)








