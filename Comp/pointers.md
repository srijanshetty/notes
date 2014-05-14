#References
References are alternate names to the same variables, so any change in
a reference cascades back to the variable it points to.

```c
int x = 0;
int &a = x;
a = 1;  // Now x is also 1
```

You can pass a reference to a function, as well as return a reference from
it. They seem much more natural to use as we don''t have to dereference them.


```c
int & echo_function(int &x) {
    return x;
}
```

#Pointers
Pointers point to memory locations which can be dereference to obtain the
values which are stored in those memory locations.

```c
int x = 0;
int* ptr = &x;
*ptr; // equals 0
```

#Constant pointers
Pointers whose value, i.e., the address stored in them cannot be changed.

```c
int x = 0;
int* const ptr = &x;
```

Note : They need to be assigned at the same time as they are declared.

# Pointers to constant
Pointers which point to constant values, i.e., the value they dereference
cannot be changed

```c
int x = 0;
const int* ptr = &x;
```

