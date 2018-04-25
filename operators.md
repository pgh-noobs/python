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

### Identity
`is`

When this operator returns true this means that each operand refers to the same piece of memory.


### Membership
`in`

This is good when you need to see if characters are in a string. 

### Negation Operators
`not`

This will turn your positive results negative and negative results positive.


### Data and operators that work together

| Data Type | Operators Allowed |
| --------- | ----------------- |
| int       | ==, !=, <=, >=, <, >, is |
| float     | ==, !=, <=, >=, <, >, is |
| complex (e.g. 3j) | ==, !=, is |
| bool      | ==, !=, <=, >=, <, >, is |
| str (string) | ==, !=, <=, >=, <, >, is, in, not |

## Logical Operators
Python uses the common logical operators of, `and`, `or`, `not`. The truth table below can be very helpful to 
understand or remember for people new to coding. It is the same in all languages.

Some will be happy to know that the Python `and`, and `or`, operators short circuit, For those that are not 
familiar with this. It means that if the first operand fails the test the other operand is not evaluated. This
can be very handy for avoiding runtime errors.

### Truth Table

|   a   |   b   | a and b | a or b | not b | a != b  |
| :---: | :---: | :-----: | :----: | :---: | :----: |
| False | False | False   | False  | True  | False  |
| False | True  | False   | True   | False | True   |
| True  | False | False   | True   | True  | True   |
| True  | True  | True    | True   | False | False  |


## Bit-wise Operators
The black art of computer programming, even for experienced developers! So, all processors and memory in a
computer work with 0's and 1's, or BITs. These operators help you change those BITs. If you want to change the 
value of a variable in the most efficient way this is it. These operators are commonly used to combine and check for flags. Flags are constant variables with
numeric value such as 1, 2, 4, 8, 16, etc. These can be combined into a single numeric value.

`&` - And

`|` - Inclusive Or

`~` - Not

`^` - Exclusive Or

`<<` - Shift Left ( m * n<sup>2</sup> this is normal math symbols )

`>>` - Shift Right ( m / n<sup>2</sup> this is normal math symbols )

|   |   `&`  |   `|`  |   `~`  |   `^`  |  `<<` (integer) |  `>>` (integer) |
| - | :----: | :----: | :----: | :----: | :----: | :----: |
|   | 0b0011 | 0b0011 |        | 0b0011 | 0b0101 (5) | 0b0101 (5) |
|   | 0b0101 | 0b0101 | ~0b01  | 0b0101 | 0b0101 << 2 | 0b0101 >> 2 |
| = | 0b0001 | 0b0111 | -0b10  | 0b0110 | 0b010100 (20) | 0b1 (1) |


