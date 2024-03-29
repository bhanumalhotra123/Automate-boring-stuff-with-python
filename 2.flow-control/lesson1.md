# Flow Control

Flow control statements can decide which python instructions to execute under which conditions.


- Boolean values
Integer, floating point, and string data type have an unlimited number of possible values.
The boolean data type has only two values: True and False

Can't use them for variable name
```py
>>> True = 54
  File "<stdin>", line 1
    True = 54
    ^^^^
SyntaxError: cannot assign to True
```

First letter should be upper case:

```py
>>> true
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'true' is not defined. Did you mean: 'True'?
>>> True
True
```

Can be stored in variables:

```py
>>> spam = True
>>> spam
True
```

## Comparison Operators

```py
>>> 42 == 42
True
>>> 42 == 99
False
>>> 2 ! = 3
  File "<stdin>", line 1
    2 ! = 3
      ^
SyntaxError: invalid syntax
>>> 2 != 3  
True
>>> 2 !=2
False
>>>
```

Can also work with other data types
```py
>>> 'hello' == 'hello' 
True
>>> 'hello' == 'Hello' 
False
>>> 'dog' != 'cat' 
True
>>> True != True
False
>>> True != False
True
>>> 42 == 42.00
True
>>>
>>> 42 == '42'
False
```
Integer and string are different for it

```py
>>> 42 < 50
True
>>> 42 > 50 
False
>>> studentcound=500
>>> studentcount=500 
>>> studentcount > 0
True
>>> studentcount >= 500
True
>>>
```

## Boolean Operators


- and
- or
- not


and
```py
>>> True and True
True
>>> True and False
False
>>> False and True
False
>>> False and False
False
```

or
```py
>>> True or False
True
>>> False or False
False
```

not
```py
>>> not True
False
>>> not not True
True
```

## Mixing Boolean and Comparision Operators

and, or, not are called boolean operators

python evaluates left value first then right.

```py
>>> (4 < 5) and (10 < 1000) 
True
>>> (4 < 5) and (10000 < 1000) 
False
>>> (4 == 5) and (10000 == 1000) 
False
```


## Elements of Flow Control

Flow control statements start with a part called __condition__, and all are  followed by a block of code called the __clause__.


### Conditions: 
Conditions always evaluate down to a Boolean value, True or False.
A flow control statement decides what to do based on whether its condition is True or False

### Blocks of Code
3 rules:
- Blocks begin when the indentation increases.
- Blocks can contain other blocks.
- Blocks endwhen the indentation decreases to zero.

```py
if name == 'Bhanu':
  print('Hello Bhanu')  --------> 1st block
if password == 'bhanuman':
  print('Access granted') -------> second block
else:
  print('Wrong Password') --------> third block
```

## Program Execution

Not all programs execute by simply going straight down
You will find the program execution jumping around the source code based on conditions, and probably skipping entire clauses.

## Flow Control Statements.  IMP

Actual decisions your programs will make

### if Statements

An if statement's clause  (that is block following the if statement) will execute if the statement's condition is true. 
The clause is skipped if condition is false.

- The if keyword
- A condition (an expression that evaluates to True or False)
- A colon
- Starting on the next line, an indented block of code (called the if clause)

### else statements
An if clause can optionally be followed by an else statement

-  The else keyword
-  A colon
-  Starting on the next line, an indented block of code (called the else clause)

### elif statements

It provides another condition that is checked only if any of the previous conditions were False.


- The elif keyword
- A colon
- Starting on the next line, an indented block of code (called the elif clause)

Once one of the statements is found to be True, the rest of the elif clauses are automatically skipped.

```py
if name == 'Bhanu':
  print('Hi Bhanu')
elif age < 5:
  print('You are not bhanu, kiddo')
elif age > 2000:
  print('You are not bhanu, immortal vampire')
elif age > 100:
  print('You are not bhanu, grannie')

```

Order of the elif statement does matter IMP

In the following case assume the user puts age as 3000 it will still output as grannie and not immortal vampire:

```py
if name == 'Bhanu':
  print('Hi Bhanu')
elif age < 5:
  print('You are not bhanu, kiddo')
elif age > 100:
  print('You are not bhanu, grannie')
elif age > 2000:
  print('You are not bhanu, immortal vampire')
```

Optionally, you can have else statements after the last elif statement.
This will guarantee that at least one (and only one) of the clauses will be executed.


## while loop statements

- The while keyword
- A condition (expression that evaluates to True or False)
- A colon
- Starting on the next line, an indented block of code (called the while clause)

Difference in if and while statement: At the end of an if clause, the program execution continues after the if statement. But at the end of a while clause
the program execution jumos back to the start of the while statement.
```py
>>> spam = 0
>>> if spam < 5:
...   print('Hello World')
...   spam = spam + 1
...
Hello World
```
```py
>>> spam = 0
>>> while spam < 5:
...   print('Hello World')
...   spam += 1
...
Hello World
Hello World
Hello World
Hello World
Hello World
```


### An Annoying while loop
```py
name = ''
while name != 'bhanu':
  print('Please type your name')
  name = input()
print('Thankyou')
```

```
$ python p.py
Please type your name
help 
Please type your name
i don't know
Please type your name
bhanu malhotra
Please type your name
bhanu
Thankyou

```


If you never enter your name , then While loop condtion will never be False, and the program will just keep asking forever.

## break Statements
If the execution reaches a break statement, it immediately exits the while loop's clause

```py
while True:   # the expression True evaluates down to value True
# the  program execution will always enter the loop and will exit only when a break statement is executed
    print('Please type your name')
    name = input()    # asks yout name
    if name == 'bhanu':  # if it is bhanu
        break #     # it breaks  ; if not jumps back to the start 
print('Thankyou')
```

```
$ python p.py
Please type your name
Bhanu
Please type your name
Bhanu Malhotra
Please type your name
bhanu
Thankyou
```


## continue statements

when program execution reaches continue statement, the program execution immediatelly jumps back to the start of the loop and reevaluates the loop's condition.

```py
while True:
    print('Who are you?')
    name = input()
    if name != 'Bhanu':
        continue
    print('Hello, Bhanu. What is your password? (Hint: It is a colour.)')
    password = input()
    if password == 'yellow':
        break
print('Access granted')
```
```
$ python p.py
Who are you?
bhanu
Who are you?
Bhanu
Hello, Bhanu. What is your password? (Hint: It is a colour.)
black
Who are you?
Bhanu
Hello, Bhanu. What is your password? (Hint: It is a colour.)
yellow
Access granted
```


## for Loops and range() Function

While loop keeps looping while its condition is True , but what if you want to execute a block of code only a certain number of times?

We do this using for loop and the range() function.

- The for keyword
- A variable name
- The in keyword
- A call to the range() method with up to three integers passed to it
- A colon
- Starting on the next line, an indented block of code (called the for clause)

```py
print('My name is')
for i in range(5):
    print('Bhanu five times ('+str(i) +')  ')
```
```
$ python p.py
My name is
Bhanu five times (0)
Bhanu five times (1)
Bhanu five times (2)
Bhanu five times (3)
Bhanu five times (4)
```

You can only use break and continue statements inside __for__ and __while__ loop only.


adding numbers from 0 to 100

```py
total = 0
for num in range(101):
    total = total + num
print(total)

```
```py
$ python p.py
5050
```

> You can use a while loop to do the same thing as a for loop; for loops are just more concise.

```py
print('My name is')
i = 0
while i < 5:
    print('Bhanu five times('+ str(i) +')')
    i += 1
```

```
$ python p.py
My name is
Bhanu five times(0)
Bhanu five times(1)
Bhanu five times(2)
Bhanu five times(3)
Bhanu five times(4)

```

### The starting, stopping, and stepping Arguments to range()

Some functions can be called with multiple arguments seperatedby a comman, and range is one of them.

```py
for i in range(2,5):
    print(i)
```
```
$ python p.py
2    ------> starts from first value only.
3
4    --------> doesn't print the last 5
```

The range function can also be called with three arguments. The first two argumentswill be the start and stop values, and third will be the step argument.

```py

for i in range(2,10, 3):
    print(i)
```

```
$ python p.py
2
5
8
```

example2 with -values
```py
for i in range(2,-10, -2):
    print(i)
```

```
$ python p.py
2
0
-2
-4
-6
-8

```

## Importing Modules

All python programs can call a basic set of functions called built-in functions, including the print(), input(), and len() functions.
Python also comes with a set  of modules called standard library.

Each modules is a python program that contains a related group of functions that can be embedded in your programs.



Before you can use functions included in a module, you must import the module with an import statement.

- The import keyword
- The name of the module
- Optionally, more module names, as long as they are seperated by commas.


```py
import random
for i in range(5):
    print(random.randint(1,100))
```

```
$ python p.py
69
59
29
93
100
```

you must type random in front of randint so as to let python know in which module it should look for the randint function.


### from import Statements

- from keyword
- module name
- import keyword
- *

with this you won't have to add random inititaly with randint while using it in code.
```py
from random import *
for i in range(5):
    print(randint(1,100))
```

```
$ python p.py
27
44
77
7
88
```

## Ending a program early with sys.exit()

How to terminate the program?

```py
import sys

while True:
    print('Type exit to exit')
    response = input()
    if response == 'exit':
        sys.exit()
    print('You typed ' + response + '.')
    print("this won't be typed")

```

```
$ python p.py
Type exit to exit
exit
```
