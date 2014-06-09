.NET
====
- It is a framework which provides a runtime called CLR (Common Language
Runtime).
- Many languages can run on CLR. Ergo .NET provides language interoperability

LINQ
====
- It is a generalization of the concept of a query language.
- The data source for link is an object. Hence any data source can be used by
LINQ as long as there exists a data provider which can covert the data source
to a queryable object.
- C# desugars the declarative syntax of LINQ into method calls.
- A LINQ provider is a library which converts a particular source in objects that
can be handled by LINQ. Additionally, they also define the standard query operators
on them.

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

# Action
- A delegate with a single input and no return

```c#
Action<int> task = delegate(int value) {
    Console.Write(value);
};
```

# Func
- A delegate which can take inputs and produce output

```c#
Func<int, int> task = delegate(int value) {
    return value;
};
```

# Lambdas
- Doh

Tasks in C#
===========
- They run in thread pools: which are essentially threads which have been
precreated and any function can be delegated to them with minimal bootstrapping
time.

// Creating a task using a constructor
Task task = new Task(new Action(FunctionName)); // Here we wrap the function by an Action
Task task = new Task(delegate { FunctionName() }); // Here we create an anonymous delegate
Task task = new Task(() => FunctionName() ); // Here we create a lambda

// We have to start these tasks explicity
task.Start();
// We can wait on tasks
task.Wait();

// To directly run a function
Task.Run(() => FunctionName());
Task.Factory.StartNew( () => FunctionName()); // For more control the following concotion works

// A continuation to the task
Task.Run(() => FunctionName()).ContinueWith(taskName => Console.Write(taskName.Result));

// A continuation to a function
task.ContinueWith(taskName => Console.Write(taskName.Result));

- The result property of tasks implicity waits on the task, so it is better to
use a continuation

- A task does not accept any arguments, but can return a result. 
    - In case it Areturns a result encapsulate the function in Func<> : Task<TResult>
    - If it does not return a result, encapsulate the function in Action : Task

- Tasks are the basic primitives for threads.
- They spawn new thread in the background.


Async/ Await pattern
======================
- These keywords do not create new threads. They are a way to manage
continuations.
- Everything that can be done by async/await can be achieved by ContinueWith
- To use the pattern, we need the follow:
    1. A LongRunningMethod
    2. A wrapper method which asynchronously runs the LongRunningMethod and
    returns a task<>
    3. An async function which awaits on the wrapper method.

```c#
private static async void CallLongRunningMethod(string message) 
```


Checked Context
===============
- A checked context is one which raises an arithematic overflow exception
    if one happens.

```c#
checked {
    // Some computation which will be checked for Overflow exception
}
```

Readonly
========
- readonly fields can be assigned to only at declaration or in constructors.

