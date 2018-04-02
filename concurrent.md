## Methods 
### Lock strategy
- Spinlock
- Semaphore
- Monitor
### Single thread
- Redis system 
- CAS
### MVCC
- OCC
- Occeanbase
### Cow
- Fock()
### Read-only / Immutable / Append-only (Assume write is much smaller than write)
- GFS/HDFS
- Occeanbase (SSD + memory)
### Log system
- Corfu
### True timestamp
- Google Spanner 
### PAXOS
- log replication 
- Occeanbase (multi-paxos, strong consistency)
### Raft / ZAB (simple multi-paxos)
- etcd 
- zookeeper
### Eventual consistency
- Gossip
- Redis
- GFS

### OS
#### lock
- Mutex
- Spinlock
- Semaphore

#### Cow
- Fork()

### Database
#### OCC and PCC
- PCC: Handle concurrency control pessimisticly. If a transaction get the lock of data resource, other transactions must wait until it ends.
Suitable environment: The cost of waiting is smaller than cost of rollback.
- OCC: Assume there are no influence among different transactions. Before commit, the transaction will check if the data update. If the data is updated, rollback to inilized state.
Suitable envrironment: The cost of rollback is smaller than waiting. 

#### Lock
- bigtable
- small table
- entry  

#### MVCC
- OCC (check if the version number is same everytime)

#### LSM


### Distributed System 
#### PAXOS 

#### RAFT and ZAB


### Cloud System





