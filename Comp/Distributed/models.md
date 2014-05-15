# Google's Map Reduce
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

# Microsoft's Dryad
- The dryad project is investigating programming models for distributed, and
parallel computation.
- The idea is to express such computation as a DAG, with each vertex being
a fragment of code/computation and the edges being channels of computation.
- A dryad job is a graph generator which can generate such DAGs.
- Drayad handles:
    - Job Creation: Conversion of program to Dryad data flow graphs.
    - Resource Mangement: Mangament of the different workers.
    - Fault tolerance
    - Job Monitoring and Visualization

## Design
- Is a distributed execution environment. A middleware between the program and the
underlying cluster architecture.
    - This allows it to be oblivious of the programming models semantics above it
    and completely focus on fault tolerance and scheduling.
- 2D pipelining.
    - grep | awk | sed
    - grep^100 | awk ^10 | sed^50
- Data partitioning.
- Is the middleware, only mainpulates the graph and has no idea of the semantics.
(Similar to the shell which is the middleware, it knows the pipeline but not the
programs in the pipeline).

## Implementation
- A job controller which only schedules.
- Vertexes are processes.
- Edges are channels which could be anything: TCP pipes, FIFO pipes, DFS, NTFS.
- Fault Tolerance
    - Every vertex stage in the pipeline has a stage manager.
    - Every connection between two stages has a connection manager.
    - These handle failures.
    - Duplication for faster execution is also managed by them.
- For associative operations which need to be aggregated finally, a middle dynamic
layer is introduced by an aggregation manager. This manager then finally aggregates
all data.
- Like map reduce, data may have to be distributed to ensure that all the same
keys land up in the same machine.

## Organization
- Windows Servers
- Cluster managers
- File System
- Dryad
- Language
    - DryadLINQ
        - C#
        - Vectors
    - Distibuted Shell
        - Legacy programs
        - C++
        - Perl
    - SQL

## References
- Add link to the MS presentation deck.

## DraydLINQ
- It is a Dryad job creator which can create Dryad computations from LINQ extensions
to C#.
