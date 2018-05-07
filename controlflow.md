# Control Flow
Because it is how we get stuff done!

## IF
The `if` statement is python is very similar to other languages. There are two real differences.
First, is that each portion or branch of the if is terminated with the colon `:`. This is a common theme 
in python. Second, is that the, else if part is abbreviated to `elif`. Use this for basic logic statements.

The `elif` branch, is a substitute for `switch` and `case` statements in other languages. So don't go
looking for `switch` and `case` statements in python, they don't exist.

``` Python
a=3
if a<3 :
    print("A is less than 3")
elif a==3 :
    print("A is equal to 3")
else:
    print("A is greater than 3")
```

## Loops
Loops allow you to perform work until a condition fails and the loop stops. In gerneral loops have two basic parts,
a condition and a code block to run. The condition will be tested everytime the code block finishes executing. 

When the code block runs there are three statements that can be used to help control the loop. First, the `break`
statement will cause the loop to exit immediately without testing the condition. Second, the `continue` statement 
will cause the code block to stop executing, test the condition and run the code block again. This is a good way
skip processing an item in a list, if that is what you loop is doing. Third, is the `pass` statement. `pass`, does
nothing, it is there so that you can make the code compile. This is handy if you just need to check a condition
until it changes.

Now python includes an `else` clause on loops. This is not a common feature across languages. The else clause is 
optional, and will only run once when the loop ends normally. Keep in mind that if the loop ends using the `break`
statement, the `else` clause will not run.

``` Python
a=0
while a<=10 :
    a+=1
else :
    print("This is the else clause")

print("a is equal to " + a)
```

``` Python
import string

a="This is a string that we can loop over, processing each character."
letters=0
white_space=0
punctuation=0
early=True

for c in a :
    if c in string.ascii_letters :
        letters+=1
    elif c in string.whitespace :
        white_space+=1
    elif c in string.punctuation :
        punctuation+=1
    elif c in string.digits :
        break
else :
    early=False
    print("else clause summary")
    print(str.format("We found {}, letters", letters))
    print(str.format("we found {}, punctuation marks", punctuation))
    print(str.format("We found {}, white space characters", white_space))

print(str.format("Did the loop end early? {}", early))
```

## Error Handling
### Syntax Errors
There are two basic errors you will get from Python, __syntax errors__ and __exceptions__.
You will see syntax errors a lot while learning Python. 
``` Python
>>> while True print('Hello world')
  File "<stdin>", line 1
   while True print('Hello world')
                  ^
SyntaxError: invalid syntax
```
The parser is going to show you earliest point where the error was detected. The little arrow
points to the token that caused the parser to notice the error. In the example the arrow is 
pointing to the `print` funtion. It was the last token evaluated that showed the error. In this
case, a `:` was missing just before the `print` function.

### Exceptions
These are more commonly referred to as runtime errors. This means your code compiled fine,
but some activity in the code is causing the application to fail.
``` Python
>>> 10 * (1/0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

### Let's Handle Them
In stead of letting an error go and crash (stop) your application, you can catch them and do something special
to keep you program running. To do this in Python we use a `try` statement. 

The `try` block is the part that you want to run and handle errors from. The `except` block is where you can put 
code to handle the error from the `try` block. The `else` block is something again that is special to python. 
The code you put in the `else` will run if there are no errors. The `finally` block is code that will run everytime, 
error or no error. This is usually a good place to put code that you want to gaurantee will run.

``` Python
try:
    # This block is the normal code you want to run.
except Exception as e:
    # This block is the code that will do thing special
    # when the specified error is thrown.
else:
    # This block run only when there are no errors.
finally:
    # This is the block that you want to gaurantee will run.
```

``` Python
def divide(x,y):
    try:
        result=x/y
    except ZeroDivisionError:
        print("You can't divide by zero")
    else:
        print("The answer is", result)
    finally:
        print("Was your division ok?")

# Notice that in Python 2.7 you get 2 and in 3.5 you get 2.0, which is a float not an int
divide(2,1)
divide(2,0)
divide("2", "1")
```

## Context blocks
Context blocks? These are what we like to call sugar, or syntactic sugar. If you look at all
the code you have to write to create a `try...finally` block it can be combersome. So the
authors of Python created this nice thing to handle cases when you need to do cleanup tasks
when the block of code is do running.
``` Python
with open("test.txt", "w") as f:
    f.write("hello world")

with open("test.txt", "r") as f:
    print(f.read())

# Better than
try:
    f = open("test", "w")
    f.write("hello world")
finally:
    f.close()
```
## Iterators
In programming there is a pattern for defining an object to support looping over its values. This pattern
is called **Iterator**. We refer to objects that use this pattern as an **Iterable**. 

For an object to be an **Iterable** in needs to implement a method named, `__iter__`. The `__iter__` method
needs to return an **Iterator** object that implements a method named, `__next__`, which is expected to return the next
object or value.

To signal that there are no more values to return the `__next__` methods just needs to raise the error `StopIteration`.

So, and **Iterable**, must implement a method named, `__iter__` and return on object that is an **Iterator**.

An **Iterator**, must implement a method named, `__next__` and return the next value in its internal list. When there
are no more values to return raise the error `StopIteration`.

``` Python
class SimpleIterable:
    def __init__(self, items):
        self.items = items

    def __iter__(self):
        return SimpleIterator(self.items)

class SimpleIterator:
    def __init__(self, items):
        self.items = items
        self.index = 0

    def __next__(self):
        if self.index >= len(self.items):
            raise StopIteration

        result = self.items[self.index]
        self.index+=1

        return result

list = SimpleIterable([1,2,3,4,5])

for item in list:
    print(item)
```

## Generators
Generators are a kind of iterator. You can only go through the values of a generator once. A generator 
is good for conserving memory with large or expensive lists. It is important to note that generators 
calculate the value each time the `__next__` method is called, this is how they conserve memory.

``` Python
class SimpleGenerator(object):
    def __init__(self, n):
        self.n = n
        self.num = 0

    def __iter__(self):
        return self

    def __next__(self):
        return self.next()

    def next(self):
        if self.num < self.n:
            cur = self.num
            self.num = self.num+1
            return cur
        else:
            raise StopIteration()

generator = SimpleGenerator(10)
for i in generator:
    print(i)
```

### Yield
The `yield` statement in python is shortcut to making a generator from a method.

``` Python
def generatorMethod(n):
    num = 0
    while num < n:
        yield num
        num += 1

generator = generatorMethod(10)
for i in generator:
    print(i)
```

## Comprehensions
Comprehensions in python are a way to create lists or generators in a compact way.

Comprehensions have four main parts.
* One of more lists
* One variable for each current list item
* One or more optional predicates
* An expression to run for each output item of the compression

For a simple example this will create a list that multiplies each item by 2.
``` Python
list=[x*2 for x in [1,2,3]]
for i in list:
    print(i)
```
In the example above the expression is `x*2`. The source list is `[1,2,3]`. And the variable is `x`.

If we want to create a list from more than one source can do the following.
``` Python
Xs=[1,2,3]
Ys=[4,5,6]
list=[x*y for x in Xs for y in Ys]
for i in list:
    print(1)
```

Now let's say we want to filter a source list. We can just add an `if` statement after the list to filter
its items. In the example below we will filter the list to only have even numbers.
``` Python
list=[x for x in range(20) if x%2==0 ]
for i in list:
    print(i)
```

Filtering can go one step further. You can provide a filter per list, as well as a final filter for all
lists at the end. In the following example we will provide two lists, each with its own filter and one last
filter.
``` Python
list=[(x, y) for x in [1,2,3,4] if x < 4 for y in [3,1,4,6] if y < 6 if x != y]
for i in list:
    print(i)
```
In the example we filtered the number 4, out of the first list. We filtered the number 6 out of the second
list. Finally we filter any output where `x` and `y` were the same value, which means we did not print a
`(1,1)` or a `(3,3)` tuple.

### Generators Again!
We had a coding pattern for creating generators and even a handy `yield` statement. Well, there is a way to create
a generator using comprehensions. In all the examples above we used square brackets `[]` to create our list. If you
replace the brackets for `()` parenthesis then you will create a generator. Let's do it for the last example above.
``` Python
list=((x, y) for x in [1,2,3,4] if x < 4 for y in [3,1,4,6] if y < 6 if x != y)
for i in list:
    print(i)
```
