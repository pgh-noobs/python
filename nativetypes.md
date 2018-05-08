# Native Types

## Numeric Types
### Integer
Python has two representations of an integer, `int`, and `long`. In other 
languages these are two very different things Python appears to treat them as 
similar things. The int type can hold values well over 2.14 billion. Try and 
see what the largest number is that you can use before python interprets it as 
a long.

### Float
Float is short for Floating point number, or a number with a decimal point.
A float uses binary floating point math. This means that 0.1 + 0.1 + 0.1 - 0.3
does not equal zero, but instead it is 5.51115123125783e-17. Yeah...this is
why you do not use the Float data type for money! That is really the gist of it. 
There are finer details about floats. If you really want to get into the details 
of it checkout the python [docs](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex) 

### Complex
A complex data type in python is just number followed by the letter `j` for the
imaginary number. If you into math and this data type is for you! You may
remember this from the talk on [Operators](operators.md)

## Byte

## Boolean

## None

## Sequence Types
Sequence types are a kind of data type that allows you do do some special things. 
This includes looping over the sequence to view the items in it. Slicing the
sequence into smaller sequences and a few others.
 
### String
A string in python is like a list of characters. But really they are a list of
bytes, each byte is the numeric value of a character in a character chart. The
chart is normally reffed to as an encoding type and the numeric value a code point.
Below are two encoding chart examples.
[ASCII](ascii.md)  
[UTF-8](https://www.w3schools.com/charsets/ref_html_utf8.asp)

### List
In python a list is kind of like an array from other languages. Since python does
not have a native array data type the list object in python is the closest thing
you have to an array. There is an array module that can be used in python
but it is not part of the basic language. 
``` Python
# This is an empty list
list=[]

# Now a list with something in it
list=[1, "2", 3.0, (4, "items")]
```

### Tuple
A tuple is set of values grouped together. This is different from a `list` or `array`. Tuples are also grouped
with similar types in python called sequence objects. Being a sequence object means you can loop over the values
it contains, test for specific values with the `in` operator.

Basics:
* Immutable - (This means you can't change them once they are created)
* Keys - You can use tuples as a dictionary key as long as all the members of the tuple are immutable
* Comparison operators work with tuples

### Using a Tuple as a function argument
You can use a tuple as a function parameter. This is sometimes called "tuple packing". In the example below
you will see that all the arguments are being gathered up into a single object.
``` Python
def add(*args):
    total=0
    for arg in args:
        total += arg
    return total

add(1,2,3)
```

If you have a tuple and want to pass it to a function that uses a tuple parameter, you first need to unpack it.
The below example is a continuation of the example above.
``` Python
def add(*args):
    total=0
    for arg in args:
        total += arg
    return total

args=(1,2,3)
add(*args)
```

### Unpacking into variables
You can unpack a tuple into variables. This is a really fun and a handy thing to do.
You must keep in mind that
``` Python
def add(*args):
    total=0
    for arg in args:
        total += arg
    return total

numbers = [1,2,3]
[a,b,c] = numbers
add(a,b,c)

x,y,z=numbers
add(x,y,z)
```

### Unpacking a tuple when you don't want the whole thing
Python 2.7 does not have basic syntax support for this. But you can do it using a slicing operator
and unpacking to a tuple or variables. The tuple of variables is important as the slicing operator
will return another tuple.
``` Python
args=(1,2,3)
(a,)=args[:1]
print(a)
```

In python 3 there is a newer syntax for tuple unpacking. Notice here the remainder is returned as
a list and not another tuple.
``` Python
args=(1,2,3)
a,*b=args
print(a)

print(b)
```

## Set

## Dict(ionary)


