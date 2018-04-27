# Python Syntax

## Syntax Rules
### Python is case sensitive
Some programming languages are case sensitive with their identifiers (variable, and function name for example).
So, in Python a variable with the name `a`, and another with the name `A`, are two different things in Python.

To try and illustrate this open the terminal and start Python
```bash
$ python
>>> a = 1
>>> A = 2
>>> print(a)
1
>>> print(A)
2
```
If this was a language that was not case sensitive, then `a` and `A` would both be equal to 2.

### Indentation defines code blocks
Python uses spaces! 4 spaces are what python uses to denote a code block.
One of the things about Python is it tries to eliminate unnecessary characters for 
defining blocks of code, like `{}` as other languages will use. This is meant to make 
Python more readable.

For example. In the below code sample the `print` function will only run when the variable `a` is
equal to `1`. The block of code is the if statement and the indented lines under it.
To end the code block just start a new line without the 4 spaces of indent.
```python
a = 1
if a == 1:
    print(a)

def foo():
    b = 1
    if b == 1:
        print(b)

foo()
```
This four spaces thing, it just keeps going. Just keep adding or removing four spaces to start or
end and code blocks.

### Comments
Okay, I know not very interesting. But they are important for the future you that will be reading your code
wondering what your intention was.

So, Python only has line level comments. Lots of languages have block level comments, not Python.

```Python
# This is a comment
```

Python does have documentation strings, which are not block comments, even though some people abuse the
language to do it.

```python
def foo():
    '''
    This is a doc string.
    '''
    print("Hello world")

foo()
print(foo.__doc__)
```

Unique to python is three double quotes. This does not comment out code but instead creates a string over
many lines of text.
```Python
a = """
This
is
a
multiline
string
"""
```

### Statement Terminators
In Python you can end a statements with a new line. You can also use a semi-colon.
```Python
print("Hello")
print("World")

print("Hello"); print("World")
```
This will fail with a syntax error/
```Python
print("Hello") print("World")
```

### Line Continuation
Sometimes you need to wrap a statement across more than one line. In python you do this with a slash.
This is mostly used in the terminal of python REPL.

```bash
$ python
>>> a = 1
>>> if a == 1: \
...     print(a)
...
1
>>>
```

### Library Import
Python scripts can include other scripts by using the `import` keyword.
```bash
$ python
>>> import sys
>>> sys.platform
'linux2'
>>>
```

