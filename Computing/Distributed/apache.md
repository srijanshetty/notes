Apache Hadoop
=============
- Hadoop is modelling exactly after Google's MapReduce implementation and consists of:
  1. Hadoop YARN: which schedules jobs
  2. Hadoop Distributed File System: For files sharing
  3. Hadoop MapReduce:
  4. Hadoop Common: The support libraries
- Hadoop is for batch Job processing.

Apache Pig
==========
- Pig is an abstraction which transpiles to Java.
- It is for easier writing of Map Reduce code.
- The language is called Pig Latin.

Apache Storm
============
- Apache Storm is a distributed realtime computation systems which works for streams of data.
  1. Distributed RPC. (Searching from databases and informing computers)
  2. Stream Processing. (Transforming data, updating databases)
  3. Continious COmputation. (Giving realtime results)

## Storm Cluster
- A storm cluster consists of a master which runs the Nimbus daemon, Nimbus is responsible for scheduling and sending data to the worker nodes which run the Supervisor daemon.
- All communication between Nimbus and Supervisor happen through a Zookeeper cluster which make sure that all nodes are fail fast. This means that any node can be killed.
- A Zookeeper is an apache project for distributed coordination and synchronization.
- All state in the workers is either kept with the Zookeeper or locally

## Topologies

### Streams
- The most important abstraction provided by Storm is a Storm Stream, which is an unbounded stream of tuples.
- A tuple is a named list of values.
- Every worker has to define the fields of the tuples that it emits.

### Nodes
- **Sprout**: A sprout emits data into the topology.
- **Bolt**: A bolt transforms the streams that it recieves.
- Each node runs a number of threads or tasks, which is essentially the parallelism level at each node.

### Workers
- The number of machines available for a task.

### Reliability Guarantee
