### Redis 
    Memory based key-value storage.

### Key Insights
- Provide data structure. 
- Use Atomic operation to guarantee concurent control.
- RDB / AOF
- Pub / Sub
- Transaction model

### Architecture
![Docker](/images/redis.jpg)
- Simple Server/Client model

### Implmentation 
- String. 
    - Add len member in object. So it can access the length of string in O(1) time. (This is also important for storing '\0' in the redis)
    - Buffer overflow. If there is memory overlap between two address, the strcat is no safe. Redis avoid this by check space first then strcat.
    - Space pre allocation. Double directly to avoid multiple time allocation.
    - Lasy free method. Not free space immediately.
- Hash
    - len element and how many nodes are used.
    - Solve hash collision by adding linkedlist.
    - Rehash when the hash factor is bigger than 5 or smaller than 5.
- List
    - Double linkedlist.
    - Add len element. O(1) time to access len.
- Set
    - intset or hashtable
- Sorted Set
    - ziplist or skiplist
    - Skip list to implement this. Log(N) average, N worse case.
- GC
    - Reference count. 