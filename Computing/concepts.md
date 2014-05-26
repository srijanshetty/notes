Parsing
=======

# Top Down Parsing
    - Recursive Descent Parsing
        Recursively find a matching lookhead and expand upon it's production
    - LL Parsing

# Bottom Up Parsing
    - Shift-Reduce Parsing
        Shift or reducee depending on the token on the stack.
    - SLR
    - LR
    - LALR

Semantics
=========

# Short Circuit evaluation:
    - Evaluate the second parameter only if needed. Examples are short circuit
    AND, OR and the like.

# Parameter Passing
    1. **Call by value:**
        Copy the value to the function
    2. **Call by reference:**
        Use the function address, to reference back to the same function
    3. **Call by need:**
        Evaluate the arguments only when needed and store this evaluations.
    4. **Call by name:**
        Copy the entire expression of the argument and evaluate every time when needed.

# Binding
    - It is the association of a value to an identifier.

## Early Binding
    - At compile time, you have assigned a type to a variable or the body to a function
    identifier.
    - In the example below, we have assigned the body to the function at compile time.

    ```c++
    void print(string name) {
        cout<<name;
    }
    ```

## Late binding
    - Here the function body is assigned to the identifier at compile time.

    ```c++
    void print(string name) {
        cout<<name;
    }

    void *pointer(string) = print;
    ```

# Dynamic Dispatch
    - Selection of the function to be called at runtime.
    - The reason for implementation is simple:
        - So, we have an object of a type, it will have a virtual function table. The vf table
        stores pointers to the function.
        - If the derived class has overridden a virtual function
        then we need to select the overridden method, else we need to select the original
        implementation.
        - This entire concept is nicely handled by pointer redirection and vft's and hence we
        need dynamic dispatch.

## Single dispatch
    - The dispatch happens only considering the object name.

    ```c++
    class Person {
        void eat() {};
    }

    class Student : Person {
        void eat() {};
    }

    Person srijan = new Student();
    srijan.eat(); // Here srijan's eat will be called
    ```

## Multiple Dispatch
    - All the parameters of a funciton and not only the object name are considered for
    dispatch.

# Static Dispatch
    - Hard code the function address directly.

## Operator Overloading
    - Operator overloading is done at compile time, hence it uses static dispatch.

    ```c++
     class Person {
         public void eat (Food f) { println ("eating food"); }
         public void eat(Pasta p) { println ("eating pasta"); }
    }

    Food food = new Pasta();
    somePerson.eat(food); // The output is 'eating food'
    ```

# Dynamic Languages
    - We have dynamically created the property 'name'.
    - Since it is an interpreted language, when obj is created,
    we have no clue that it can have such a property. Hence, we cannot
    allocate space beforehand, same is true for functions.
    - Hence we say that the list of methods can be altered at runtime.

    ```javascript
    var obj = {};
    obj['name'] = 'srijan';
    ```

References
==========
    - [http://condor.depaul.edu/ichu/csc447/notes/wk10/Dynamic2.htm]
    - [http://philogb.github.io/blog/2009/02/08/generic-functions-and-javascript/]
