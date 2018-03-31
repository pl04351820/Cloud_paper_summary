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
Basic type
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

Exposed type 
Keyword: ENCODING to check the encode type of redis.
- String 
    - int, raw or smbstr. SET number 10086. -> integer. if integer > 2 ^ 32. It will become SDS to store the value.
- List
    - Ziplist or linkedlist
        Transfer from ziplist to linkedlist if a string is very big or number of elements is big.
- Hahs
    - ziplist / hashtable
- Set 
    - Intset / hashtable
- Ordered set 
    - ziplist / skiplist(Important)


### Feature in single database
1. In redis, the key is stirng variable, and value can be one of the above data structure.
2. Object will owns a hashtable for expiration time in redis. The implementation of this is based on expires dictionary. (The key is a pointer to object, the value is the time)
3. Strategy for deleting an expired keys 
    - Timer delete. High cost, high performance. (Good for memoery, but for CPU)
    - Lazy delete. Verify when everytime delete the keys. 
    - Event delete.
    In redis, use lazy delete and event delete strategy.

### RDB and AOF
RDB is more like snapshot and AOF is more like log system. You can close them to get performance like memcached.
Choose between RBD and AOF. If the user is more sensitive to the security of data in redis. AOF is better because RDB will lose part data in cache. RDB (5s) .. AOF (1s). The default method for recovery of redis is AOF. Redis use fork syscall to backup data.

### Event handler in redis
File event: communicate through socket. Based on select, epoll, evport, kqueue
Time event: Run specific event in specific timestamp.

### Concurrency Control 
The redis concurrency control is based on single thread strategy to avoid concurrency.