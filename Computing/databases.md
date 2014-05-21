Databases
=========
# Data-warehouse
- This collects information from different databases.
- This is meta data about databases, used for queries by
higher level management.

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

Transactions
============
An indivisible operation is called a transaction. A transaction must fail or
suceed, it cannot be partially complete.

# Transactional Memory
    - Allows a group of load store operations happen atomically.

# Software transactional memory
    - It is a concurrency control mechanism.
    - Just like database transactions, access to shared memory is transactional.

Reasoning about transactions
============================
# Serializable transactions
A way to reason about transactions, it gurantees that transactions can be thought
of as happening serially.

# Eventual consistency
- Transactions will be eventually applied.
- A transaction will be applied to some replica and finally all of them will be
    copied into all records.
- The order of transactions is not honoured.
