## Flow Control

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

# Comparison Operators

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

# Boolean Operators



