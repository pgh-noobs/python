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
So now the answer is false. This is because the two lists **are** different objects whereas the 
integer value 1, in each variable points to the **same** object. If we look at the assembly code that
python creates we can see that the integers point to the same constant integer values.
```bash
 $ python
1 >>> import dis
2 >>> dis.dis(compile('1000 is 1000', '<stdin>', 'eval'))
3   1           0 LOAD_CONST               0 (1000)
4               3 LOAD_CONST               0 (1000)
5               6 COMPARE_OP               8 (is)
6               9 RETURN_VALUE
```
Looking at the byte code that printed, you can see that each line for loading the value 1000, is using
the LOAD_CONST byte operator. This means that the value 1000, is from the same memory address.
