# Native Types

## Integer
Python has two kinds of integers. `int`, and `long`. In other languages these are two very different things
Python appears to treat them as similar thing. The int type can hold values well over 2.14 billion.
Try and see what the largest number is that you can use before python interprets it as a long.

## Float

## Complex

## String

## Byte

## Boolean

## None

## List

## Tuple
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
```
>>> def add(*args):
...     total=0
...     for arg in args:
...         total += arg
...     return total
...
>>> add(1,2,3)
6
```

If you have a tuple and want to pass it to a function that uses a tuple parameter, you first need to unpack it.
The below example is a continuation of the example above.
```
>>> args=(1,2,3)
>>> add(*args)
6
```

### Unpacking into variables
You can unpack a tuple into variables. This is a really fun and a handy thing to do.
You must keep in mind that
```
>>> numbers = [1,2,3]
>>> [a,b,c] = numbers
>>> add(a,b,c)
6
>>> x,y,z=numbers
>>> add(x,y,z)
6
```

### Unpacking a tuple when you don't want the whole thing
Python 2.7 does not have basic syntax support for this. But you can do it using a slicing operator
and unpacking to a tuple or variables. The tuple of variables is important as the slicing operator
will return another tuple.
```
>>> args=(1,2,3)
>>> (a,)=args[:1]
>>> a
1
```

In python 3 there is a newer syntax for tuple unpacking. Notice here the remainder is returned as
a list and not another tuple.
```
>>> args=(1,2,3)
>>> a,*b=args
>>> a
1
>>> b
[2,3]
```

## Set

## Dict(ionary)


