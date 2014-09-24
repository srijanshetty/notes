Acceptance, Rejection and Loop
==============================
We are given for a specification of a languages. For example given an encoding
of a Turing machine and a string does the TM accept the string or not. Now we
have to create a turing machine which tells us whether a random encodign belongs
to this language or not. That is, we are checking for membership.
At any given point of time, we only know a subset of strings which belong to
this langauge. Of course, if we knew the entire set of strings which belonged to
this langauge, we are essentaily done.

Decider
-------
A decider can enumerate the entire set for us. Because it can tell whether a
string belongs to this language or not.

Recognizer
----------
A recognizer on the other hand gives us a "current" subset of strings which it
has accepted. For other strings it may loop. This looping could be indefinite or
it could mean that after a lot of time the string may get accepted or rejected.
So, in essence we cannot enumerate the entire set of the language.

Deciders is a model of computation, this means that it has limitations. So, are
TM. The only problem is that we asssume that TM are the most powerful model of
computation that we have.

Problems are unsolvable because of their intinsic hardness. Acceptance problem
is hard because we cannot determine if the TM will loop on an input or not.
