# X-bit aligned:
If something in memory is x-bit aligned, this means we can only occupy the
memory locations which are multiples of x.
Example 4 byte aligned means, that the memory locations in which data will be
placed are 0, 4, 8, 16 ..

# Necessary and sufficient:

        -------------------------
        | N -----------------   |
        | E | C ---------   |   |
        | C | O |       |   |   |
        | E | N | SUFF  |   |   |
        | S | D |       |   |   |
        |   |   ---------   |   |
        |   -----------------   |
        -------------------------

# Multiple Infinite Paths:
Taking multiple paths a single step at a time ensures that we reach multiple
infinites. Taking a single infinite path can lead us to a single infinity.

# Infinite Sets

## Elements in an infinte set:
- A set is countable if there exists a bijective between the set and N. 
- Countable union of countable sets is countable.
- Finite union of finite sets is finite.

## Cantor's Diagonalization:
R is uncountable as proved by Cantor's Diagonalization proof. To prove a set is
uncountable, just set up a correspondence or bijective between that set and R.
Or use the diagonalization method which is far more easier.

# GCD
The ingenious idea behind this algorithm is the fact that

    gcd(a,b) = gcd(b, a-b) if b<a

We can extend this idea further and take a mod b instead of a-b.
The proof of this fact is simple.

    b = d.k
    a = d.m
    b-a = d(k-m)

Now if d is the gcd(a,b) then it is the greatest number that divides both a and b.
Also, every other divisor of a and b is a divisor of the gcd. So the greatest divisor
of b and b-a will be the gcd(a,b).
