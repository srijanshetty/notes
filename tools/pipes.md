Recepies
========
# Unique items from a list
sort | uniq -c | sort -nr

# Cut according to some delimiter
cut -d" " -f1

# When piping refer to stdin/stout
Use '-'

xargs
=====
- When you want to use stdin as arguments you use xargs

```shell
echo 1 2 3 4 | xargs -n 4
```

- Deal with whitespace in stdin ( -0 )
- Argument list marker

```shell
find . -type f -name "*.bak" -print0 | xargs -0 -I {} mv {} /backup/
```

Paste
=====
- Use to join stuff together
- '-s' joins in a single argument
- '-d' specifies the delimiter while joining

Cut
===
- opposite of paste
- '-d' delimiter to split on
- '-f' displays the fields

bc
==
- Calculator

expr
====
- Evaluates the expression passed to it as arguments

let
===
- Evaluate expressions

Composition
===========
- Composition is achieved by $()
