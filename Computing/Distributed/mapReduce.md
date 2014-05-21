Google's Map Reduce
===================
- An abstraction for parallel, distributed data tasks.
- The programmer need only write two functions and a specification
object which provides the tuning parameters.
- Map: take key/values and convert them into intermediate key/values
    MAP: map(k1, v1) -> (k2, v2)
- Reduce groups all the similar keys from the above steps and then
runs the reduce task on each key.
    REDUCE: reduce(k2, list(v2)) -> list(v2)

## Implementation
- The input data is divided into M splits.
- A master program then assigns workers to work on these M partitions.
- After a worker completes a map task, it informs the master of its status.
- The worker splits its output into R partitions with the function
    hash(key) mod R
    - This ensures that same keys go into the same partition.
- Now the master assigns the R reduce tasks to workers.
- A reduce worker takes the corresponding partition from each map worker's
local file system.
- The output created by reduce workers is stored in the global file system.

## Important Ideas
- The distributed File System partitions the input files and makes copies
into the workers.
- Intermediate results are only stored in the map workers and are obtained
using RPC.
- **Locality Optimization**: Master schedules workers who have a local copy of
the input data in order to save network bandwidth.
- **Fault Tolerance**: The master pings each worker periodically. If it
does not respond then its completed tasks are marked idle and so are
its in progress tasks. All reduce workers are also informed of this development.
- **Backup tasks**: The last few tasks are performed by multiple workers
because of the problem with stranglers (machines which are performing a task
slowly).
- The number of workers should be less than M and R. This ensures that each
worker has to perform multiple tasks. This makes sure that each worker is busy
at any given point of time. (Additional benefit is when faults happen, recovery is
fast).

