-------------------------------------------------------------------------------
Imperative Programming:
This is a programming paradigm which resembles the way code is executed in a
machine, it is very low level in some sense.
It is mostly sequential programming, with a lot of manipulation of program state

We have constructs like:
    1. loops
    2. if
    3. case

A variable represents a memory location and we can directly manipulate it.
-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
Declarative Programming:
Instead of giving a series of steps to accomplish a task, we essentially spell
out what the program is supposed to do. For example consider the quicksort
program in haskell

>quicksort [] = []
>quicksort (x:xs) = smaller xs ++ x ++ larger xs
        where smaller y = [ z | z<-y, z<=x]
              larger y  = [ z | z<-y, z>x]

Here we have define what quicksort does rather than give a series of steps to
accomplish the task. Very common approaches of declarative programming are:
    Functional
    Logic

There is very little or no manipulation of state
-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
Concurrent Programming:
In case of concurrent programming we have multiple threads which are running
together. Note together here does not mean they are running simultaneously; the
threads can be running parallely or they may run with pre-emption.

Two models are used for synchronization:
    1. Message Passing
    2. Shared memory

There's also this concept of atomic commits or transactional memory in case of
concurrency. An atomic commit or a transaction is a set of operations which are
atomic, they are performed together or are not performed at all. This ensures
consistency in the data at the Data Center.
-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
Object Oriented Programming:
Object oriented programming consists of classes, which encapsulate methods and
variables together. It provides abstraction by the means of public, private and
protected members.

The relation "is a" is an dependence relation and is captured by 
inheritance: single, multiple etc.

The relation "has a" is an aggregation relation which is what encapsulation
stands for.
-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
Polymorphism:
Parametric polymorphism is to write a function generically so that it handles
all types identically. Such polymorphism in the OOP world is called parametric
polymorphism while in the functional world it is called plain polymorphism.
The programming paradigm is called generic programming.

Ad hoc polymorphism or overloading is when a function can have multiple
implementaions depeding on the number and types of arguments. This is called
function overloading or method overloading.
-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
