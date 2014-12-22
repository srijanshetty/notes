Google's Map Reduce
===================

- An abstraction for parallel, distributed data tasks.
- The programmer need only write two functions and a specification object which provides the tuning parameters.
- Map: take key/values and convert them into intermediate key/values

```
    MAP: map(k1, v1) -> (k2, v2)
```

- Reduce groups all the similar keys from the above steps and then runs the reduce task on each key.

```
    REDUCE: reduce(k2, list(v2)) -> list(v2)
```

### Implementation
- The input data is divided into M splits.
- A master program then assigns workers to work on these M partitions.
- After a worker completes a map task, it informs the master of its status.
- The worker splits its output into R partitions with the function


```
    hash(key) mod R
```

- This ensures that same keys go into the same partition.
- Now the master assigns the R reduce tasks to workers.
- A reduce worker takes the corresponding partition from each map worker's local file system.
- The output created by reduce workers is stored in the global file system.

### Important Ideas
- The distributed File System partitions the input files and makes copies into the workers.
- Intermediate results are only stored in the map workers and are obtained using RPC.
- **Locality Optimization**: Master schedules workers who have a local copy of the input data in order to save network bandwidth.
- **Fault Tolerance**: The master pings each worker periodically. If it does not respond then its completed tasks are marked idle and so are its in progress tasks. All reduce workers are also informed of this development.
- **Backup tasks**: The last few tasks are performed by multiple workers because of the problem with stranglers (machines which are performing a task slowly).
- The number of workers should be less than M and R. This ensures that each worker has to perform multiple tasks. This makes sure that each worker is busy at any given point of time. (Additional benefit is when faults happen, recovery is fast).

GFS
===

### Assumptions
- Nodes fail often
- Append is the common operation

### Design Decisions
- Differers from POSIX (slightly)
- snapshot and append are new calls.

### Implementation
- A single master whose state has a fine grained check pointing.
- Other nodes are data nodes.
- A file is stored in 64MB chunks and the master has a record of the chunk mapping.
- Replicas of the chunks is kept in many nodes.
- The map may go out of sync so, nodes send digest messages to the master.

### Read
- Master sees the map and tell the client which directly communicates.

### Write
- Master tells the client the mapping.
- The data node tries a write, asks other nodes to write. This operation may fail.
- A lock called lease is handed over to the primary when writing for consistency.

### Append
- A failed append may be due to node failure or write fail.
- The former is solved by re-sync with master. In the latter, junk is added to the file.
- The onus is on the client to replay the message.


Collossus
=========
- Successor to GFS
- Uses database triggers which run every time some data is entered into the database.
- Triggers are costly and not performant. So we can safely assume that Google had to employ some Frankenstein hacks and ingenious engineering to make them performant.

Millwheel
=========
- Like storm, it has topologies.
- Each node is called a computation and it subscribes to streams.
- A tuple is a (key, value, timestamp) triple
- Each computation provides a key extractor and only selects some tuples from a stream.
- There are three good ideas:
    1. Idempotency by keeping track of each production. This requires committing bookkeeping information from each node and checking for duplication every time a node receives a tuple.
    2. Low watermark which is a sort of global timeline indicating the amount
    of work left throughout the system.
    3. Persistent storage: Spanner and BigTable are the backing store.
- Strong productions are used, which means that a production is committed before sending down the wire.
- Each computation is issued a sequencer and if it fails, the new node is issued another sequencer, this prevents zombie writes to the database.
- A single master which maintains the entire database is present.
