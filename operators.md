# Operators

## Numeric Operators

Operator | Meaning | Example
-------- | ------- | -------
`+` | Add two numbers. Also called a unary operator | `print(1+2) # 3` `+3`
`-` | Subtract two number. Also called a unary operator | `print(2-1) # 1` `-3`
`*` | Multiplication. Also called a binary operator | `print(2*2) # 4`
`/` | Division. *Caution* with python 2.7 and 3. Also a binary operator | `print(4/2) # 2`
`**` | Exponent, or Power. This too is a binary operator | `print(2**2) # 4`
`//` | Floor division. This means the remainder is ignored, not rounded off. Again binary operator| `print(11//3) # 3`
`%` | Modulo division. This returns the remainder of the division operation | `print(11%3) # 2`

### Imaginary Numbers
So, imaginary numbers. In Python you can do math with imaginary numbers. In math you might remember that the
imaginary number was represented with an _i_, in Python it is _j_. 

Try this with all the operators. You might be surprised at the result.
`print(3j+3j)`

### Implicit Conversion
Implicit conversion is when Python automatically will converts the value from one type to another for you.
Python arithmetic operators will convert values of one type to another in a specific order from bool to complex.
You cannot implicitly convert back the other. For example 1.5 cannot convert to 1 or 2, it's just not the same thing.
But 1 can convert to 1.0, they are roughly the same thing.

bool to int,
int to float, 
float to complex (or those funny imaginary numbers)

### Explicit Conversion
Explicit conversion is where you have to tell Python to perform the conversion. This usually means that you 
are asking to convert a value to a type that Python will not do implicitly because you may lose data. However;
you can convert values up and down the type order mentioned above.

## String Operators
Simple, `+`, `*`. The first `+` concatenates two strings. The second `*` repeats a sequence of characters the
number of type specified by the integer operand.

```
>>> "abc" + "def"
>>> "abcdef"
>>>
>>> "abc" * 3
>>> "abcabcabc"
```

## Relational Operators
Python can compare data in several ways. Each operator will return true or false, and not all operators can be
used with all the basic types of data.

### Symbolic
`==, !=, <, >, <=, >=`

### Identifiers
`is, in`

### Compound operators
`not in`

Data Type | Operators Allowed
--------- | -------
int | ==, !=, <=, >=, <, >, is
float | ==, !=, <=, >=, <, >, is
complex (e.g. 3j) | ==, !=, is
bool | ==, !=, <=, >=, <, >, is
str (string) | ==, !=, <=, >=, <, >, is, in, not in

