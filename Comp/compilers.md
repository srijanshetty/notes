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
- Call by refernce:
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

### References
- [http://condor.depaul.edu/ichu/csc447/notes/wk10/Dynamic2.htm]
