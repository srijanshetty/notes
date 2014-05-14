# Data-flow programming
Unlike traditional imperative/procedural/control-flow programming, in which the program
is a sequence of steps which runs from top to bottom, in data flow programming, the
program is a series of data transformations.
It is best visualized as a DAG with each vertex a function that acts on its input to
produce output. All vertexes are independent and can perform their operation as soon
as all its required inputs are met.
So, data-flow programming in inherently parrallel.
