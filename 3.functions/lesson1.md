# Functions

A function is like a mini-program within a program.


The major purpose of function is to group code that gets executed multiple times.

```py
def hello():        # defines a function  and the following code is the body 
    print('Bhanu!')
    print('Bhanu!!!')
    print('Hello there!')

hello()
hello() # function calls   When program execution reaches this, it jumps to the start of the function and excutes the code in it
```

```
$ python p.py
Bhanu!
Bhanu!!!
Hello there!
Bhanu!
Bhanu!!!
Hello there!
```

## def statements with parameters
When you call print() or len(), you pass in values, called arguments in this context, by typing them between the parantheses. You can also define your own function that accepts arguments.

Value stored in parameter (it is basically a variable) is forgotten when the function returns.

```py
def hello(name):            # here name is the parameter
    print('Hello'+ ' ' + name)
hello('Bhanu')
hello('Bhanuman')        # Bhanuman is the argument
```
```
$ python p.py
Hello Bhanu
Hello Bhanuman
```


## Return Values and return statements

The value that a function evaluates to is called the return value of the function.

A return statement consists of the following:

- The return keyword
- The value or expression that the function should return

```py
import random

def getAnswer(answerNumber):
    if answerNumber == 1:
        return 'Hello1'
    elif answerNumber == 2:
        return 'Hello2'
    elif answerNumber == 3:
        return 'Hello3'
    else:
        return 'no hello'



print(getAnswer(random.randint(1,9)))

```
```

$ python p.py
Hello1


$ python p.py
Hello2


$ python p.py
Hello3


$ python p.py
Hello2

$ python p.py
no hello

```