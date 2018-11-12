## Operators

* `*`: multiplication
* `/`: floating point division
* `//`: integer division
* `%`: modulus division
* `is`: checks for equality of identity - do two references refer to the same object?

Integer division (the `//` operator) always moves left on the number line:

```
7 / 4 = 1.75
7 // 4 = 1

-6 / 4 = -1.5
-6 // 4 = -2
```

The `*` operator works on strings, performing repetition.

```
'python' * 3
pythonpythonpython
```

---

## Scalar Types and Values

* `int`: arbitrary precision integers
* `float`: 64-bit floating point numbers
    * IEEE-754 double precision
    * 53 bits of binary precision
    * 15 to 16 bits of decimal precision
* `None`: the null object
* `bool`: boolean logical values

---

## Relational Operators

* `==`: value equality/equivalence
* `!=`: value inequality/inequivalence
* `<`: less-than
* `>`: greater-than
* `<=`: less-than or equal to
* `>=`: greater-than or equal to

---

## Strings

* `str`: immutable sequences of Unicode codepoints

* Multiline strings are delimited by 3 quote characters:
```
"""This is
    a multiline
    string"""
```

* `\n`: universal newlines 
    * [PEP 278](https://www.python.org/dev/peps/pep-0278/)

* Raw strings are prefixed with `r` and don't require escape sequences:
```
path=r`c:\home\some\long\path'
```

---

## Bytes

* Immutable sequences of byes
* `b'data'`

---

## Lists

* Mutable sequences of objects
* List literals are delimited by square brackets and list items are comma separarated: 
    * `[a, b, c, d]`
* List indexes are zero based

---

## Dictionairies

* Mutable mappings of keys to values
* Dictionaries are delimited by curly braces
* Each key/value is separated by a comma
* Each key is separated from the value by a colon

```
{k1: v1, k2: v2, ...}
```

---

## Type Converter Functions

* `int`: for floating point numbers, it *discards* the decimal portion and moves *towards* zero on the number line
* `float`
* `str`

```
int(3.14)
3

int(3.999)
3

int(3.0)
3
```