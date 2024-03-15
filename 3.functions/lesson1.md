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

## The None Value

In python there is a value called None, which represents the absence of a value.

Must be typed with capital n

Behind the scenes, python adds return statement to the end of any function definition with no return statement.

```py
>>> a = print('hi')
hi
>>> None == a       
True
>>>
```





In Python, when you assign the result of the print() function to a variable a, it will always return None. The print() function in Python is designed to print values to the console, but it doesn't return anything. Therefore, when you assign the result of print('hi') to a, a gets assigned the value None.


## Key Arguments and Print

Keyword arguments in Python allow you to pass arguments to a function by specifying the parameter names along with their corresponding values. 

```py
print('hello')
print('world')
```
```
python p.py
hello
world
```
```py
print('hello' , end= '')
print('world')
```
```
python p.py
helloworld
```

```py
print('cats', 'dogs', 'buffalo')
```
```
python p.py
cats dogs buffalo
```
```py
print('cats', 'dogs', 'buffalo', sep='+')
```
```
python p.py
cats+dogs+buffalo
```
We will learn how to add keyword arguments to the functions we write but later when we would have learnt about list and dictionary data types.


## Local and Global Scope

Variables inside a function are said to exists in function's local scope.
Variables that are assigned outside of all the functions are said to exists in function's global scope.


When your program begins global scope is created.
When your program ends global scope is destroyed.

A local scope is created when a function is called.
When the function returns local scope is destroyed and variables are forgotten,


- Code in the global scope cannot use any local variables.
- However a local scope can access global variables.
- Code in a local scope cannot use variables in any other local scope.
- You can use the same name for different variables if they are in different scopes.(for example a variable named bhanumalhotra123 in local scope as well as in global scope. Or in two different local scopes.)

While using global variables in small programs is fine, it is a bad habit to rely on global variables as your program gets larger and larger.



### Local variables cannot be used in global scope
```py
def spam():
    laughs = 123

spam()
print(laughs)

```
```
python p.py
Traceback (most recent call last):
  File "C:\Users\HP\Desktop\automate_with_python\p.py", line 5, in <module>
    print(laughs)
          ^^^^^^
NameError: name 'laughs' is not defined
```

### Local scopes cannot be used in other local scopes

```py
def spam():
    hills = 123
    jam()
    print(hills)


def jam():
    hills = 0
    lakes = 312

spam()
```
```
python p.py
123            # it doesn't take the value from jam function as ;  as soon as jam function returns its local scope get destroyed. 
```

### Global variables can be read from a local scope

```py
hills = 33
def spam():
    print(hills)

spam()
```
```
python p.py
33
```

### Local and global variables with the same name

```py
def spam():
    hills = 'spam local'
    print(hills)

def jam():
    hills = 'jam local'
    spam()
    print(hills)

hills = 'global'
jam()
print(hills)
```

```
python p.py
spam local
jam local
global
```

You should avoid using same name for variables in different scopes.
If you wanna get confused you can, good luck!

## The global statement

If you want to modify a global variable from within a function, use the global statement.

```py
hills = 'global123'
def spam():
    global hills
    hills = 'localspam123'
spam()                            # if we don't call the spam function(it changes the value of hills set globally, we will still get the output as global123)
print(hills)
```

```
python p.py
localspam123   
```


#### Four rules to tell whether a variable is in local scope or global scope:
- If variable is used outside of all the functions, then it is always a global scope.
- If there is a global statement for that variable in a function, it is global variable.
- If the variable is used in an assignment statement in a function, it is a local variable.
- If the variable is not used in an assignment statement in a function, it is a global variable.


```py

def spam():
    global hills
    hills = 'spam'   # this is a global variable of which we are changing the value at global level.
```
```py
def jam():
    hills = '123' # this is local
```
```py
def tom():
    print(hills) #this is global as we haven't defined value locally
```
```py
hills = 123 #this is global
spam()
print(hills)
```

#### Can't use a local variable before defining it, you will get an error.

```py
def spam():
    print(hills)
    hills= 'www'
hills = 123
spam()

```
```
python p.py
Traceback (most recent call last):
  File "C:\Users\HP\Desktop\automate_with_python\p.py", line 5, in <module>
    spam()
  File "C:\Users\HP\Desktop\automate_with_python\p.py", line 2, in spam
    print(hills)
          ^^^^^
UnboundLocalError: cannot access local variable 'hills' where it is not associated with a value
```



## Exception Handling

You want the program to detect errors, handle them, then continue to run.

Errors can be handled by try and except statements.

The code that could potentially have an error is put in a try clause.
The program execution moves to the start of a following except clause if an error happens.

```py
def spam(divideBy):
    try:
        return 42 / divideBy
    except ZeroDivisionError:
        print('Error: Invalid Argument')

print(spam(2))
print(spam(12))
print(spam(0))
print(spam(1))
```

```
python p.py
21.0
3.5
Error: Invalid Argument
None  -----> shows the function didn't return anything when divided by 0
42.0
```




Any error that occurs in function calls in a try block will also be caught.
```py
def spam(dividedBy):
    return 42 / dividedBy
try: 
    print(spam(2))
    print(spam(12))
    print(spam(0))
    print(spam(1))
except ZeroDivisionError:
    print('Error: Invalid Argument')
```

```
python p.py
21.0
3.5
Error: Invalid Argument
```
The reason print(spam(1)) is never executed is because once the execution jumps to the code in the except clause. Instead it just keeps moving down as normal.

## A Short Program: Guess the Number