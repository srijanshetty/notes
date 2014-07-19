Threads vs Tasks
================
- Threads are heavy weight OS threads which need to be spawned
  every time that they are created, leading to a performance
  overhead.
- Tasks are actions which are sheduled to be run on an existing
  thread pool and as such require no boot up time. They are
  meant to perform small tasks and not long running operations.
  Albeit the TaskScheduler can be informed that the Task needs
  to performa a heavy duty operation in which case, it can
  schedule it on a seperate thread.

Concurrency
==========

# Mutex
- Also called a lock, is a primitive for Mutual Exclusion.
- Mutex : **Mut**ual **Ex**clusion

# Semaphore
- It's a concurrency primitive which allows multiple access
  to the entity is guards.
- They are used to control access to resources which are
  limited in number.

# Semaphore vs Mutexes
- Consider a room with only one key, this is the case of a
  mutex. If we have four identical rooms with the same key
  that can open each of them, we have a semaphore.

# Monitors
- They provide for Mutual exclusion and waiting for a condition
  to become true.
- They provide a mechanism to signal the waiting thread when
  the condition becomes true.

# Deadlock
- When a thread has a lock and it goes to sleep. In such a
  case the thread is dead and other threads are starving.

# Livelock
- Consider a situation where we have two threads and each
  require two locks. If each of the thread gets a lock and
  gives it up because the other one acquired the other one;
  and the second thread does the same, we have a livelock.
- This is identical to the situation where two people are
  coming from opposite sides and are stuck because both take
  steps in the same direction.

# Race condition
- When a thread tries to write to a DS and another thread
  tries to read off the DS, we have a race condition.

Thread Safe
===========
- A data structure is thread safe, if multiple threads can
  access the DS concurrently and yet the DS remains in a
  consistent state.
- A function is thread safe if multiple threads can run the
  function concurrently, i.e., the function is being run
  in multiple threads concurrently.

Re-entrant
==========
- A reentrant function does not access static variables or
  return a reference to any static variable.
- They can be run by a task, paused and resumed and still
  will have the desired effects.
- This is because all their state is stored with the function
  itself.




