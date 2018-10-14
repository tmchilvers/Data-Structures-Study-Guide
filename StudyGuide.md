# Algorithm Analysis 
_Algorithm_: A process or set of rules to be followed to solve a problem
	
## 1. Empirical (Experimental) Analysis
Analysis performed by implementing two algorithms and run an experiment with the same input.
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
* Upper Bound.

_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) <= c*g(n) for all n > n<sub>0</sub>_

### Little O Notation
* **Strict** Upper Bound.

_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) < c*g(n) for all n > n<sub>0</sub>_

### Big Omega Notation
* Lower Bound

_Given two functions, f(n) and g(n), f(n) = O(g(n)) if there exists two constants c and n<sub>0</sub> such that f(n) >= c*g(n) for all n > n<sub>0</sub>_

### Little Omega Notation
* **Strict** Lower Bound

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
An array (abstract data type) is a collection of individual data values with two distinguishing characteristics:
* Any array is ordered. You must be able to count off the values: here is the first, here is the second, and so on.
* An array is homogeneous. Every value in the array must have the same type.
## Arrays as data structures 

### Benefits 
* Multiple data items of same data type can be accessed using single name
* Can implement matrices
* Can be implemented other data structures 
### Disadvantages
* Must know in advanced
* Arrays are _static_
* Insertions and deletions are VERY difficult and time consuming
### How to create/initialize an array 
* As with any other variable, arrays must be declared before you use them. In C++, the most common syntax for declaring an array variable looks like this:
 
```cpp
Type name[size];
```
 
Where _type_ is the element type, _name_ is the array name, and _size_ is an integer representing the number of elements.
 
EX. 
```cpp
int intArray[10];
```

* (Arrays do not automatically initialize to null)
### How does an array differ from other data structures (i.e. Linked Lists, Trees) 
* Elements in an array are stored consecutively in memory
* Arrays have a constant size (static)
## Big-O Runtime 
### Access 
* O(1) Constant
### Insert 
* O(1) Constant
### Search 
* O(n) Linear
### Delete 
* O(1) Constant

# Linked List/ Double Linked List 
A _concrete_ data structure type.
* A _Double-Ended_ Linked List allows insertion at the tail
### Benefits
* Lists are _dyanamic_
* can grow and shrink during run time
* Insertion and Deletion operations are easier
* Efficient Memory Utilization (no need to pre-allocate memory)
* Faster access time
* Linear Data structures (stacks, queues) can be easily implemented using Linked list
### Disadvantages  
* Use more memory than array due to pointers
* Nodes in a linked list must be read in order from the beginning as linked lists are inherently sequential access.
### How to create/initialize a Linked List
```cpp
NaiveList::NaiveList()
{
  front = NULL;
  size = 0;
}

NaiveList::~NaiveList()
{
  //food for thought
}

unsigned int NaiveList::getSize()
{
  return size;
}

void NaiveList::printList()
{
  ListNode *curr = front;

  while(curr != NULL)
  {
    cout << curr->data << endl;
    curr = curr->next;
  }
}

void NaiveList::insertFront(int d)
{
  ++size;
  ListNode *node = new ListNode(d);
  node->next = front;
  front = node;
}

int NaiveList::removeFront()
{
  --size;
  int temp = front->data;
  ListNode *ft = front;
  front = front->next;
  ft->next = NULL; //nullptr

  delete ft;

  return temp;
}

int NaiveList::find(int value)
{
   int idx = -1;
   ListNode *curr = front;

   while(curr != NULL) //begin search for value
   {
     idx++;

     if(curr->data == value) //we found it
     {
       break;
     }
     else //we did not find it continue searching
     {
       curr = curr->next;
     }
   }

   if(curr == NULL)
   {
     idx = -1;
   }

  return idx;
}

int NaiveList::deletePos(int pos)
{
  int idx = 0;

  ListNode *curr = front;
  ListNode *prev = front;

  while(idx != pos) //this loop is responsible for putting our pointers in their correct positions
  {
    prev = curr;
    curr = curr->next;
    ++idx;
  }

  //found the position, lets proceed to delete

  prev->next = curr->next;
  curr->next = NULL;

  int d = curr->data;
  size--;

  delete curr;

  return d;
}
```
### How to create a node
```cpp
ListNode::ListNode()
{
  //Implement this
}

ListNode::ListNode(int d)
{
  data = d;
  next = NULL; //nullptr
}

ListNode::~ListNode()
{
  //research this
}
```
### How does a list differ from other data structures (i.e. arrays, Trees)  
* Elements are not stored consecutively in memory
* Linked list is dynamic, the size can change
### Difference between **Single** and **Double** Linked Lists
* Double allows efficient deletion, fetching end nodes, and flexible iteration
* Single is more memory efficient and better for systems with limited resources
* Double is the most commonly implemented List
## Big-O Runtime 
### Access 
* O(n) Linear
### Insert 
* O(1) Constant (only at front and back of DE list)
* O(n) Linear at any other position
* O(1) Always constant for Double Linked List
### Search 
* O(n) Linear
### Delete 
* O(1) Constant (only at front and back of DE list)
* O(n) Linear at any other position
* O(1) Always constant for Double Linked List


# Abstract Data Structures (ADT)  
## Stacks (LIFO) 
## Queues (FIFO)
### Circular queue 
### Priority queue  
## Definition of an ADT  
* Defined by their interface (functionality) rather than by their implementation.

## Implementation 
### Arrays based Stacks
```cpp
GenStack::GenStack() {
  myArray = new char[10];
  size = 10;
  top = -1;
}

GenStack::GenStack(int maxSize) {
  myArray = new char[maxSize];
  size = maxSize;
  top = -1;
}

GenStack::~GenStack() {
  delete myArray;
  cout << "Stack Destroyed" << endl;
}

void GenStack::push(char d) {
    if (top >= size-1) {
    std::cout << "Stack full. Could not push " << d << endl;
  }
  else {
    myArray[++top] = d;
  }
}

char GenStack::pop() {
    if (top < 0) {
    std::cout << "Stack empty. Nothing to pop." << endl;
  }
  else {
    return myArray[top--];
  }
}

char GenStack::peek() {
  return myArray[top];
}

bool GenStack::isFull() {
  return (top == size-1);
}

bool GenStack::isEmpty() {
  return (top == -1);
}
```

### List based Stacks
```cpp
GenStack::GenStack() {
  myList = new LinkedList[];
 }

GenStack::~GenStack() {
  delete myList;
  cout << "Stack Destroyed" << endl;
}

void GenStack::push(char d) {
    myList.insertFront(d);
 }

char GenStack::pop() {
    return myList.removeFront();
}

char GenStack::peek() {
  return myList->front;
}

bool GenStack::isEmpty() {
  return myList->front == NULL;
}
```

# Trees  
## Benefits  
* logarithmic search and insert is faster than the linear runtime of other data structures
## Disadvantages  
* Runtime slows when tree is unbalanced
* Deletion is slow
## How does a tree (BST.) differ from other data structures (i.e. arrays, linked list)  
* BSTs have faster searching and inserting 
## Rules of a Tree o Binary Search Tree (BST)  
* A binary search tree is a binary tree storing keys or kv entires at its interval nodes nad satisfying the following property:
* Entries are sorted
* Values smaller than root, left subtree
* Values greater than root, right subtree
* Each node (vertex) must have exactly one path (edge) to another node
If not then it’s a graph
* Nodes that have two children are called internal nodes
* That have one or fewer children are called external nodes
* Leaf nodes have no children
* Depth same as tree
* Height same as a tree
* The number of children of a given node is called the degree

## Big-O Runtime 
### Access 
* O(log(n)) Logarithmic Runtime
### Insert 
* O(log(n)) Logarithmic Runtime
### Search
* O(log(n)) Logarithmic Runtime







