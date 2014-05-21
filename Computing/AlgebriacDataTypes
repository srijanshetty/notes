
ADT:
    An algebraic data type is made up by the composition of other types either
    by a product or a sum operation. Ex:

    data Tree a = EmptyTree | Node (Tree a) a (Tree a)

    The above Tree data type is an algebraic datatype which can be represented
    algebraically as

    T = 1 + a * T^2

    (The 1 over here indicates an empty type). So essentially there are two
    componenets to the ADT Tree. It is the disjoint union of either an EmptyTree
    or a Node, i.e., at a time it can be either but not both and the Node type
    in turn is a product type consisting of three components: two trees and a
    value. It should be noted that the Node value constructor needs to be
    furnished all three of these entites in order to be valid. This tree type
    can be represented in C as

    enum treeType {EMPTY, NODE};

    struct Tree {
        enum treeType tag;

        Union Data {
            struct Node {
                struct Tree *left;
                struct Tree *right;
                int value;
            };
        };
    };

    Size of this dataType on a 64 bit machine would be - note in a 64 bit
    machine, all addresses are alligned at 8 byte locations.

    Size of tag = 8
    Size of EmptyTree = 0
    Size of Node = allign(8 + 8 + 4)
                 = 24

    Size of datatype = 32 bytes

Product type:
    This type represents a combination of two different types of entites tied
    together. The best example is the cartesian product A x B, or a tuple (A,B).
    If we have tuple we can get the individual type of element back.
    A Haskell example is

    data Exp = Plus Int Double

    Exp is a data type which has an element Plus which is a product type of Int
    and Double

Disjoint Union:
    The idea of disjoint union is that it is a union of different elements in
    which you know exactly which set a particular element belongs to. The best
    example is illustrated by Haskell.

    data Either a b = Left a | Right b

    Here Either is a Disjoint Union type. So, each element is an element of
    Either and it can be either Left a or Right b. 

Enums:
The correct way to use an enum is:

    enum values {FIRST,SECOND};
    enum values some_value = FIRST;

Unions:
The correct way to use a union is:

    union Data {
        int i;
        float f;
    } data;

    data.i = 10;
    data.f = 10.0;

    // Note the value of data.i gets corrupted once we initialize it with data.f

At a time a union holds only one piece of information, also the size of a union
data type is the largest of it's elements

