### STL library 
One of bigest part in the CPP standard library.

Philosophy: Resuability Improvement. Divide the data structure with algorithm
    -> Decrease coupling

#### 
- Containers(Data structure to store data): vector, list, deque, set, map.
- Algorithms: sort, serach, copy, erase
- Iterator
- Functors 
- Adapters 
- Allocators: Memory configuration and management.

#### Containers
Two containers in STL: sequence containers / associative containers.
- vector (Array)
    An array that can store and compress any kind of the data. (Dynamic allocation automatically.)
    * pushback, assgin, at, begin, end.
    * The extendsion method: Allocate more resources on memory at a time to reduce multiple requests. (Same as redis strategy: Extend to twice large space).
    * Random Access Iterators (start, finish, end_of_storage iterators to see the limit of memeory space.)
    * Continuous memory allocation
- list
    * Random memeory allocation (Extend space for one new allcation at a time. --> no waste). Hence the list will add or remove element in a constant time. 
    * Double linked list. Provide bidirectional iterators.
- stack and queue is based on adapters.
    * Continuous memory locaition. 

#### Iterator
Difference between iterator and generator. Iterator is a design pattern that encapsulate the data that provide interface to outside. Generator is a stategy that calculate the real data in runtime environment. (Lazy Evatuation)

In STL, the iterators are more like the glue between containers and algorithms. The iterator can pointer to the object in the containers. Algorithm can acccess to the location of containers, but not wrong about their types.

#### Algo
- Sort
- Copy
- Remove
- Swap
Why sort is so fast in STL:
    non-recursive Mergesort 