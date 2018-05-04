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
```
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
``` Bash
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

```
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

```
def divide(x,y):
    try:
        result=x/y
    except ZeroDivisionError:
        print("You can't divide by zero")
    else:
        print("The answer is", result)
    finally:
        print("Was your division ok?")

divide(2,1)
divide(2,0)
divide("2", "1")
```

## Context blocks
```
with expression as variable, expression as variable :
    do something with the variables
```


## Iterators & Generators

### Yield

## Comprehensions

