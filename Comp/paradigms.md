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

## Interfaces
- They are abstract classes, they only specify the functions that need to be
implemented and the dirty work of implementing them is left to each and every
class that derive from them.
- So, we can say that a class matches an interface.
- The idea is really powerful and extensible. We can have a interface callled
iterable and anything that wants to iterate should match the specifications
of the interface. Then the for loop can be designed to work with iterables.

## Subtyping

```c++
class Base {
}

class Child : Base {
}

Base[] items = new Base[10];
item[0] = new Child();
```

- here it doesn't matter that the array is of Base, because
Child will have all of Base's methods.
- The compiler will only use the name of methods of Base,
and they will be present in the virtual function table of Child.
- Also dynamic dispatch will be needed here because we have no clue
if Child overides any methods of Base.
- It is not necessary to have late binding, because we know for sure
that such a method exists.
- Subtyping means that anywhere the supertype can be used, the subtype can
be used.

# Generic Programming
- The central idea of generic programming is write code which can work for
all types, i.e., parametric polymorphism is the impetus of this style of
coding.
- Functional languages have a transparent support for generic programming.
- C++ family of languages use templates to implement this

```c
template <typename T>
class Stack {
    T list[];

    void Stack<T>::push(T item);

}
```

- Similarly we can have generic functions as well.
