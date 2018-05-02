# Control Flow
Because it is how we get stuff done!

## IF
The `if` statement is python is very similar to other languages. There are two real differences.
First, is that each portion or branch of the if is terminated with the colon `:`. This is a common theme 
in python. Second, is that the, else if part is abbreviated to `elif`. Use this for basic logic statements.

The `elif` branch, is a substitute for `switch` and `case` statements in other languages. So don't go
looking for `switch` and `case` statements in python, they don't exist.

```
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
a="This is a string that we can loop over, processing each character."
letters=0
white_space=0
punctuation=0

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
    print("else clause summary")
    print("We found " + letters + ", letters")
    print("we found " + punctuation + ", punctuation marks")
    print("We found " + white_space + ", white space characters")

print("Did the loop end early?")
```

## Error Handling
```
try:
    do something
except
```

## Context blocks
```
with expression as variable, expression as variable :
    do something with the variables
```


## Iterators & Generators

## Comprehensions
