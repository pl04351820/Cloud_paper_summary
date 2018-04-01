#### Communication between process.
- Pipe. Only works for half dual mode. The relationship usually parent and child or assembler.
- Message Queue. (msgget msgsnd syscall)
- Signal. Singal_kill  
- Shared Memory. Very fast --> Ctrl + C and Ctrl + V (mmap)
- Socket Networking 

#### Communication between threads.
- Global variable 
- Message queue
- CEvent (Event method)
#### Coroutine
- Thread accesses resource when there is free resources.
- Coroutine accesses resouce avoiding meanningless work. Avoid context switch. But this actually lose the ability for multi-thread. (Yeld)
- Implementation is create space on Heap. Then thread synchronization them.