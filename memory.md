#How Does Memory work in Python

## Object references
```bash
$ python
>>> a = 1
>>> A = 1
>>> print(a is A)
True
```
But wait should that not be false! No. 

Let's look at one more thing.
```bash
$ python
>>> a = []
>>> A = []
>>> print(a is A)
False
```
So now they answer is false. This is because here the two lists ARE different objects whereas the integer value 1, in each variable points to the SAME object.
If we look at the assembly code that python creates we can see that the integers point to the same constant integer values.
```bash
$ python
>>> import dis
>>> dis.dis(compile('1000 is 1000', '<stdin>', 'eval'))
  1           0 LOAD_CONST               0 (1000)
              3 LOAD_CONST               0 (1000)
              6 COMPARE_OP               8 (is)
              9 RETURN_VALUE
```

