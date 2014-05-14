# Parsing
## Top Down Parsing
- Recursive Descent Parsing
    Recursively find a matching lookhead and expand upon it's production
- LL Parsing

## Bottom Up Parsing
- Shift-Reduce Parsing
    Shift or reducee depending on the token on the stack.
- SLR
- LR
- LALR

# Semantics
## Short Circuit evaluation:
Evaluate the second parameter only if needed. Examples are short circuit
AND, OR and the like.

## Parameter Passing
- Call by value:
    Copy the value to the function
- Call by reference:
    Use the function address, to reference back to the same function
- Call by need:
    Evaluate the arguments only when needed and store this evaluations
- Call by name:
    Copy the entire expression of the argument and evaluate every time when
    needed.

## Binding
It refers to the association of a value to an identifier. This could mean anything
from association of a value to a variable, code to a function etc.

## Dynamic Dispatch
Selection of the function to be called at runtime.
The reason for implementation is simple:
- So, we have an object of a type, it will have a virtual function table. The vf table
stores pointers to the function.
- If the derived class has overridden a virtual function
then we need to select the overridden method, else we need to select the original
implementation.
- This entire concept is nicely handled by pointer redirection and vft's and hence we
need dynamic dispatch.

## Static Dispatch
- Hard code the function address directly.

# Dynamic Languages

```javascript
var obj = {};
obj['name'] = 'srijan';
```
- We have dynamically created the property 'name'.
- Since it is an interpreted language, when obj is created,
we have no clue that it can have such a property. Hence, we cannot
allocate space beforehand, same is true for functions.
- Hence we say that the list of methods can be altered at runtime.

## Late binding
- Due to the above reasons, we have to late bind all references to variables
using a hash table (or like v8, we can use hidden classes)
- Late binding is also done using function pointers. That is we assume that
the function's address is stored in some function pointer and we use that pointer.

### References
- [http://condor.depaul.edu/ichu/csc447/notes/wk10/Dynamic2.htm]
