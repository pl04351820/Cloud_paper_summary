#### Method for synchronization 
- mutex: Only one object can access the resource at a time.
- signal(Semaphore): Many objects can access resource but within a limit.
- event: send a update request when finishing. 

#### Communication between threads
- Pipe. Only works for half dual mode. The relationship usually parent and child or assembler.
- Message Queue. RabbitMQ, ZeroMQ
- Signal. Singal_kill  
- Shared Memory. Very fast --> Ctrl + C and Ctrl + V
- Socket Networking

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