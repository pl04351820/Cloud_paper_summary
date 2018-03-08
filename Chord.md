## DHTs ( Distributed hashtable key-value pair.)
Operation to support:
- Insert
- Find
- Search

---
How to disteibute the keys?
How do you search the keys?
How do you handle membership change?
How to replication? (Sharding + Replication)

--- 
Chord answer:
k = hash(key) % 2^m     [0, 2^m)
node = hash(key) % 2^m  [0, 2^m)

2^m is the size of key stores.
nodes only know the key it stores.

---
1. Naive way. Sequential search O(n) time and O(1) space. O(1) is because only store the information of its sucessor.
2. O(log(n)). Use space to trade time here. Table called Finger.
(k + 2^i)  i = 0, 1, 2, ..., m-1. <- Table size.

---
Problem 
1. Networking partition. The error handle is leaved to higher level.
2. Weak consistency implementation. 
3. Not scaleable due to networking parition problem.


---
Where is replication in this system?
Store keys in different ndoes many times.

---
DHT is not guarantee transaction(ACID).
Transaction needs extra lock to implement.  -- Shadow 
Fixed order to gurarantee the transaction... Every operation should be in order in this system. --> Flattering

--- 
- Hotspot  
1. Storage hotspot
2. Request hotspot

Storage load balance is achieved by consistent hash. --> use virtual node to solve this problem.
request hotpsot is achieved by vary more nodes.