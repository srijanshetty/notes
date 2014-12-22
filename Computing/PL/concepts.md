Imperative Programming
======================

Also called as control flow programming, procedural programming This is a programming paradigm which resembles the way code is executed in a machine, it is very low level in some sense.

It is mostly sequential programming, with a lot of manipulation of program state

We have constructs like:
    1. loops
    2. if
    3. case

A variable represents a memory location and we can directly manipulate it.

Declarative Programming
=======================
Instead of giving a series of steps to accomplish a task, we essentially spell out what the program is supposed to do. For example consider the quicksort program in haskell

```hs
quicksort [] = []
quicksort (x:xs) = smaller xs ++ x ++ larger xs
        where smaller y = [ z | z<-y, z<=x]
              larger y  = [ z | z<-y, z>x]
```

Here we have define what quicksort does rather than give a series of steps to accomplish the task. Very common approaches of declarative programming are:
  1. Functional
  2. Logic

There is very little or no manipulation of state

Concurrent Programming
======================

In case of concurrent programming we have multiple threads which are running together. Note together here does not mean they are running simultaneously; the threads can be running parallely or they may run with pre-emption.

Two models are used for synchronization:
  1. Message Passing
  2. Shared memory

There's also this concept of atomic commits or transactional memory in case of concurrency. An atomic commit or a transaction is a set of operations which are atomic, they are performed together or are not performed at all. This ensures consistency in the data at the Data Centre.

Generic Programming
===================

- The central idea of generic programming is write code which can work for all types, i.e., parametric polymorphism is the impetus of this style of coding.
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

Object Oriented Programming
===========================

Object oriented programming consists of classes, which encapsulate methods and variables together. It provides abstraction by the means of public, private and protected members.

The relation *is a* is an dependence relation and is captured by inheritance: single, multiple etc.

The relation *has a* is an aggregation relation which is what encapsulation stands for.

## Polymorphism:

Parametric polymorphism is to write a function generically so that it handles
all types identically. Such polymorphism in the OOP world is called parametric
polymorphism while in the functional world it is called plain polymorphism.
The programming paradigm is called generic programming.

Ad hoc polymorphism or overloading is when a function can have multiple
implementaions depeding on the number and types of arguments. This is called
function overloading or method overloading.

## Inheritance

### Virtual functions
They are functions that can be overridden by the derived class.

### Extension Methods
- While most classes have instance methods which can be called upon any type
- C# has the notion of extension methods, which can extend any interface and type
  - These extension methods look exactly like the instance methods during call.
  - The advantage is that they allow the base classes to be modified without changing them.

### Interfaces
- They are abstract classes, they only specify the functions that need to be implemented and the dirty work of implementing them is left to each and every class that derive from them.
- So, we can say that a class matches an interface.
- The idea is really powerful and extensible. We can have a interface callled iterable and anything that wants to iterate should match the specifications of the interface. Then the for loop can be designed to work with iterables.

```c#
interface Base {
    public void someMethod();
}

class Child : Base {
    Base.someMethod() {
        // Write the definition over here
    }
}
```

### Subtyping

```c++
class Base {
}

class Child : Base {
}

Base[] items = new Base[10];
item[0] = new Child();
```

- here it doesnt matter that the array is of Base, because Child will have all of Bases methods.
- The compiler will only use the name of methods of Base, and they will be present in the virtual function table of Child.
- Also dynamic dispatch will be needed here because we have no clue if Child overides any methods of Base.
- It is not necessary to have late binding, because we know for sure that such a method exists.
- Subtyping means that anywhere the supertype can be used, the subtype can be used.

### Abstract Classes
- Classes for which you want no objects
- They only serve as base classes.

### 'base' keyword
- This is used to invoke the constructor of the base class from a derived class.

### 'this' keyword
- Refers the current object. Can be also used to call some constructor

Parsing
=======

### Top Down Parsing
- Recursive Descent Parsing: Recursively find a matching lookahead and expand upon its production
- LL Parsing

### Bottom Up Parsing
- Shift-Reduce Parsing: Shift or reduce depending on the token on the stack.
- SLR
- LR
- LALR

Binding
=========

- It is the association of a value to an identifier.

### Early Binding
- At compile time, you have assigned a type to a variable or the body to a function
identifier.
- In the example below, we have assigned the body to the function at compile time.

```c++
void print(string name) {
    cout<<name;
}
```

### Late binding
- Here the function body is assigned to the identifier at runtime.

```c++
void print(string name) {
    cout<<name;
}

void *pointer(string) = print;
```

Dispatch
========

### Dynamic Dispatch
- Selection of the function to be called at runtime.
- The reason for implementation is simple:
  - So, we have an object of a type, it will have a virtual function table. The vf table stores pointers to the function.
  - If the derived class has overridden a virtual function then we need to select the overridden method, else we need to select the original implementation.
  - This entire concept is nicely handled by pointer redirection and vfts and hence we need dynamic dispatch.

### Single dispatch
- The dispatch happens only considering the object name.

```c++
class Person {
    void eat() {};
}

class Student : Person {
    void eat() {};
}

Person srijan = new Student();
srijan.eat(); // Here srijans eat will be called
```

### Multiple Dispatch
- All the parameters of a function and not only the object name are considered for dispatch.

### Static Dispatch
- Hard code the function address directly.

### Double dispatch in C++
At first glance, double dispatch appears to be a natural result of function overloading. Function overloading allows the function called to depend on the type of the argument. Function overloading, however, is done at compile time using "name mangling" where the internal name of the function has the argument's type encoded in it. So for example a function foo(int) would internally be called __foo_i and function foo(double) would be called __foo_d. So there is no runtime overhead because there is no name collision and calling an overloaded function goes through at most one virtual table just like any other function. Dynamic dispatch is only based on the type of the calling object. Consider the following example, written in C++, of collisions in a game:

```c++
class SpaceShip {};
class ApolloSpacecraft : public SpaceShip {};

class Asteroid {
public:
  virtual void CollideWith(SpaceShip&) {
    cout << "Asteroid hit a SpaceShip" << endl;
  }
  virtual void CollideWith(ApolloSpacecraft&) {
    cout << "Asteroid hit an ApolloSpacecraft" << endl;
  }
};

class ExplodingAsteroid : public Asteroid {
public:
  virtual void CollideWith(SpaceShip&) {
    cout << "ExplodingAsteroid hit a SpaceShip" << endl;
  }
  virtual void CollideWith(ApolloSpacecraft&) {
    cout << "ExplodingAsteroid hit an ApolloSpacecraft" << endl;
  }
};
```

If you have

```c++
Asteroid theAsteroid;
SpaceShip theSpaceShip;
ApolloSpacecraft theApolloSpacecraft;
then, because of function overloading,

theAsteroid.CollideWith(theSpaceShip);
theAsteroid.CollideWith(theApolloSpacecraft);
```

will print Asteroid hit a SpaceShip and Asteroid hit an ApolloSpacecraft respectively, without using any dynamic dispatch. Furthermore

```c++
ExplodingAsteroid theExplodingAsteroid;
theExplodingAsteroid.CollideWith(theSpaceShip);
theExplodingAsteroid.CollideWith(theApolloSpacecraft);
```

will print ExplodingAsteroid hit a SpaceShip and ExplodingAsteroid hit an ApolloSpacecraft respectively, again without dynamic dispatch.

With a reference to an Asteroid, dynamic dispatch is used and

```c++
Asteroid& theAsteroidReference = theExplodingAsteroid;
theAsteroidReference.CollideWith(theSpaceShip);
theAsteroidReference.CollideWith(theApolloSpacecraft);
```

prints ExplodingAsteroid hit a SpaceShip and ExplodingAsteroid hit an ApolloSpacecraft, again as expected. However,

```c++
SpaceShip& theSpaceShipReference = theApolloSpacecraft;
//note the type of the pointer and the type of the object.
theAsteroid.CollideWith(theSpaceShipReference);
theAsteroidReference.CollideWith(theSpaceShipReference);
```

The desired behaviour is to bind these calls to the function that takes theApolloSpacecraft as its argument, as that is the instantiated type of the variable, meaning the expected output would be Asteroid hit an ApolloSpacecraft and ExplodingAsteroid hit an ApolloSpacecraft, but the output is actually Asteroid hit a SpaceShip and ExplodingAsteroid hit a SpaceShip. The problem is that, while virtual functions are dispatched dynamically in C++, function overloading is done statically.

The problem described above can be resolved by simulating double dispatch, for example by using a visitor pattern. Suppose SpaceShip and ApolloSpacecraft both have the function

```c++
virtual void CollideWith(Asteroid& inAsteroid) {
  inAsteroid.CollideWith(*this);
}
```

Then, while the previous example still does not work correctly, the following does:

```c++
SpaceShip& theSpaceShipReference = theApolloSpacecraft;
Asteroid& theAsteroidReference = theExplodingAsteroid;
theSpaceShipReference.CollideWith(theAsteroid);
theSpaceShipReference.CollideWith(theAsteroidReference);
```

It prints out Asteroid hit an ApolloSpacecraft and ExplodingAsteroid hit an ApolloSpacecraft, as expected. The key is that theSpaceShipReference.CollideWith(theAsteroidReference); does the following at run time:

```c++
theSpaceShipReference is a reference, so C++ looks up the correct method in the vtable. In this case, it will call ApolloSpacecraft::CollideWith(Asteroid&).
```

Within ApolloSpacecraft::CollideWith(Asteroid&), inAsteroid is a reference, so inAsteroid.CollideWith(this) will result in another vtable lookup. In this case, inAsteroid is a reference to an ExplodingAsteroid so ExplodingAsteroid::CollideWith(ApolloSpacecraft&) will be called.

Type Systems
============

### Duck Typing
- In static type systems, the type of an object determines what operations it can perform and the compiler enforces this at runtime.
- Dynamic type systems do the same but at run time.
- In duck typed languages, the programmer can call any method on any object.
- Its up to him to make sure that the object in question has the particular method.
- Duck typed systems issue a runtime error if the method is not found.

General Concepts
================

### Short Circuit evaluation
- Evaluate the second parameter only if needed. Examples are short circuit AND, OR and the like.

### Parameter Passing
1. **Call by value:** Copy the value to the function
2. **Call by reference:** Use the function address, to reference back to the same function
3. **Call by need:** Evaluate the arguments only when needed and store this evaluations.
4. **Call by name:** Copy the entire expression of the argument and evaluate every time when needed.

### Operator Overloading
- Operator overloading is done at compile time, hence it uses static dispatch.

```c++
 class Person {
     public void eat (Food f) { println ("eating food"); }
     public void eat(Pasta p) { println ("eating pasta"); }
}

Food food = new Pasta();
somePerson.eat(food); // The output is 'eating food'
```

### Sugar
A syntactic construct which is converted into its equivalent at compile time.

```
obj.method() -> method(obj)
```

### Reflection
- Reflection allows you to determine the properties/fields of an object at compile time and use them.
- It inspects the metadata to see if an object/type contains a method/field.

```js
if ( obj.method ) {
    obj.method();
}
```

- Here we check the existence of the method and only then call it.

Dynamic Languages
=================
- We have dynamically created the property 'name'.
- Since it is an interpreted language, when obj is created, we have no clue that it can have such a property. Hence, we cannot allocate space beforehand, same is true for functions.
- Hence we say that the list of methods can be altered at runtime.

```javascript
var obj = {};
obj['name'] = 'srijan';
```

References
==========
- [http://condor.depaul.edu/ichu/csc447/notes/wk10/Dynamic2.htm]
- [http://philogb.github.io/blog/2009/02/08/generic-functions-and-javascript/]
