Microsoft's Dryad
=================

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

# Design
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

# Implementation
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

# Organization
- Windows Servers
- Cluster managers
- File System
- Dryad
- Language
    - DryadLINQ
        - C#
        - Vectors
    - Distibuted Shell
