### Google filesystem
    Master and Chunk server.

#### Key Insights
- Change the size of chuck to reduce metadata.
- Append-only strategy to avoid synchronization.
- Erasure coding to reduce the cost of replication.
- Bloom filter algorithm to locate resource fast.

#### Read 
    direct read anyone of replication.

#### Write
    pipeline write.

#### Feature
    - Weak consistency.

