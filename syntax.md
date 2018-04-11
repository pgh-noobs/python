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

### Indentation define code blocks or scope
Python uses spaces! 4 space is what python uses to denote a code block.
One of the things about Python is it tries to eliminate the unnecessary use characters for 
defining blocks of code, like `{}` as other languages will use. This is meant to make 
Python more readable.

For example. In the below code sample the `print` function will only run when the variable `a` is
equal to `1`. To end the code block just start a new line without the 4 spaces of indent.
```python
a = 1
if a == 1:
    print(a)
```

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

