Object and Collection Initializers
==================================
- Any object van be initialized at runtime using the following syntax

```c#
Container cont = new Container {
    name = "srijan",
    id = 1
};
```

Anonymous types
===============
- Using new {} we can create an anonymous type.
- C# creates a new class definition for each anonymous type.

dynamic
=======
- C# allows an object to be defined dynamic so that all method
    dispatched become dynamic dispatch.
- Compile time type checking is not done for such types.


Delegates
=========
- Typed encapsulation of function pointers.

```c#
public delegate double someFunction(double value);
```

Actions
=======
- A delegate with a single input and no return

```c#
Action<int> task = delegate(int value) {
    Console.Write(value);
};
```

Func
====
- A delegate which can take inputs and produce output

```c#
Func<int, int> task = delegate(int value) {
    return value;
};
```

Lambdas
=======
- D'oh

Checked Context
===============
- A checked context is one which raises an arithematic overflow exception
    if one happens.

```c#
checked {
    // Some computation which will be checked for Overflow exception
}
```

Abstract Classes
================
- Classes for which you want no objects
- They only serve as base classes.

Readonly
========
- readonly fields can be assigned to only at declaration or in constructors.
