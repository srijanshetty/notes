Vectored I/O
============
- Also called scatter/gather.
- **Scatter:** Read from memory and divide it into multiple buffers
    atomically.
- **Gather:** Read from multiple buffers into memory atomically.

Latency
=======
- I/O takes a lot of time and this time is called latency.
- Owing to this asynchronous IO is preferred.
