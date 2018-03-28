#### Method for synchronization 
- mutex: Only one object can access the resource at a time.
- signal(Semaphore): Many objects can access resource but within a limit.
- event: send a update request when finishing. 

#### Deadlock situation
- mutext 
- unpreempt 
- request and hold 
- circuit wait

#### State of threads
- Ready
- Running
- Wait

#### Buffer overflow
- Stack increase very fast, and replace some key datas.

#### Algo for thread schedule
- FCFS
- Priority 
- Round-Rbin

#### Algo for Cache
- LRU
- LFU
- FIFO

##### Critical Section -> A area where resource are shared. 

#### I/O multiplex
- Select
- epoll (Linux)
- kqueue (BSD/ Mac OS X)

#### RAID 
- RAID 0: No replication. Only improve performance
- RAID 1: replication 
- RAID 2: Use hamming code
- RAID 3: Parity code
- RAID 4: Use chuck instead of block
- RAID 5: Allocate parity codes into different disks.
- RAID 6: Add more parity bit.