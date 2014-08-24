Transactions
============
An indivisible operation is called a transaction. A transaction must fail or
suceed, it cannot be partially complete.

# Transactional Memory
- Allows a group of load store operations happen atomically.

# Software transactional memory
- It is a concurrency control mechanism.
- Just like database transactions, access to shared memory is transactional.

ACID
====
The ACID principles have to be followed by any database in order for it to be called
reliable.

# Atomicity
- This means every transaction is a *all or nothing* deal, either the transaction
    goes through completely or it doesnt happen at all.

# Consistency
- Consistency is specified by the domain.
- When we say that a database is consistent, we mean that it follows whatever
    consistency rules that have been set forth by the domain before and after
    a transaction.

# Isolation
- Isolation requires that a transaction happens in an isolated fashion on its own
    copy of the database.
- This ensures that the database is not affected by any other transaction.

# Durability
- Durablilty is a gurantee that if any transaction gets committed, then it stays
    in the memory for sure.

    # Availability
        - Even if one of the data-centers fail, we should be able to access our data.
            This property is called availabilty.

    # Resilience
        - If any of the data-centers fail, we have a backup data-center.

Consistency Models
====================
# Serializable transactions
A way to reason about transactions, it gurantees that transactions can be thought
of as happening serially.

# Eventual consistency
- Transactions will be eventually applied.
- A transaction will be applied to some replica and finally all of them will be
    copied into all records.
- The order of transactions is not honoured.

# Quorum Consistency
- The transaction is committed only a quorum of databases have committed it.

# Timeline Consistency
- The master gets updated and a timeline is replayed to the secondarys, which
    are either at the same level as the master or lagging behind.

Consistency vs Availability(Latency/Response Time) Debate
==================================
- We can have relaxed consistency for availability.
- A buisness like hotels may want high availability, hence it allows for double
    bookings as it always has extra rooms.

Scaling
=======
# Horizontal Scaling
- Adding more nodes to the cluster and partitioning the data

# Vertical Scaling
- Keeping the data in one place but adding more compute power to the server.

# Data-warehouse
- This collects information from different databases.
- This is meta data about databases, used for queries by
higher level management.

Databases
=========
# Data-center
- A group of networked computer servers used for remote storage and
distribution of large amount of data.
- They had redundant power suppy, network supply.
- Might consume as much power as a small town.
- Plus they need air conditioning.

Service Level Agreement
=======================
A clause in a service contract.

Bulk Loading
============
- Usually data is inserted one at a time in a database.
- Bulk loading allows a chunck of data to be inserted into the
    database at once.

Reference
=========
- Availability: Low latency
- Fault Tolerant: Reliable, replication
- Distributed: Scalability
- Performance: Throughput/Latency
- Consistency:

