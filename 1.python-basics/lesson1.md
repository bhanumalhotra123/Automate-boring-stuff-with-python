```py
$ python
Python 3.12.2 (tags/v3.12.2:6abddd9, Feb  6 2024, 21:26:36) [MSC v.1937 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 2+2
4
```

Expression - 2+2
Values 2
Operator - +


Even the following is an expression without an operator
```
>>> 2
2
```

http://nostarch.com/automatestuff/

Here's the table with operators sorted by precedence:
```
| Operator | Description | Example |
|----------|-------------|---------|
| ** | Exponentiation | 2 ** 3 gives 8 |
| - | Unary negation | -x |
| + | Unary positive | +x |
| ~ | Bitwise NOT (complement) | ~x |
| * | Multiplication | 5 * 3 gives 15 |
| / | Division | 10 / 2 gives 5.0 |
| % | Modulus (remainder of division) | 10 % 3 gives 1 |
| // | Floor division (division discarding any remainder) | 10 // 3 gives 3 |
| + | Addition | 2 + 3 gives 5 |
| - | Subtraction | 7 - 2 gives 5 |
| << | Left shift | 5 << 2 gives 20 |
| >> | Right shift | 5 >> 2 gives 1 |
| & | Bitwise AND | 5 & 3 gives 1 |
| ^ | Bitwise XOR | 5 ^ 3 gives 6 |
| \| | Bitwise OR | 5 \| 3 gives 7 |
| < | Less than | 2 < 5 gives True |
| <= | Less than or equal to | 3 <= 3 gives True |
| > | Greater than | 7 > 4 gives True |
| >= | Greater than or equal to | 6 >= 8 gives False |
| == | Equal to | 5 == 5 gives True |
| != | Not equal to | 5 != 3 gives True |
| in | Membership (checks if a value exists in a sequence) | 5 in [1, 2, 3, 4, 5] |
| not in | Negated membership | 6 not in [1, 2, 3, 4, 5] |
| is | Identity (checks if two objects are the same) | x is y |
| is not | Negated identity | x is not y |
| not | Logical NOT | not True gives False |
| and | Logical AND | True and False gives False |
| or | Logical OR | True or False gives True |
| = | Assignment | x = 5 |
| += | Add and assign | x += 3 (equivalent to x = x + 3) |
| -= | Subtract and assign | x -= 2 (equivalent to x = x - 2) |
| *= | Multiply and assign | x *= 4 (equivalent to x = x * 4) |
| /= | Divide and assign | x /= 2 (equivalent to x = x / 2) |
| //= | Floor divide and assign | x //= 3 (equivalent to x = x // 3) |
| %= | Modulus and assign | x %= 3 (equivalent to x = x % 3) |
| **= | Exponentiate and assign | x **= 2 (equivalent to x = x ** 2) |
| &= | Bitwise AND and assign | x &= 3 (equivalent to x = x & 3) |
| ^= | Bitwise XOR and assign | x ^= 3 (equivalent to x = x ^ 3) |
| \|= | Bitwise OR and assign | x \|= 3 (equivalent to x = x \| 3) |
| <<= | Left shift and assign | x <<= 2 (equivalent to x = x << 2) |
| >>= | Right shift and assign | x >>= 2 (equivalent to x = x >> 2) |
```
```py
$ python
Python 3.12.2 (tags/v3.12.2:6abddd9, Feb  6 2024, 21:26:36) [MSC v.1937 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 2 + 3
5
>>> (2+3)* 6
30
>>> 2**8
256
>>> 23//7
3
>>> 23 %3
2
>>> (5 - 1)* ((7+1)/(3-1)) 
16.0
>>>
```
python will keep on evaluating parts of the expression until it becomes a single value.

```py
>>> (5 - 1)* ((7+1)/(3-1)) 
16.0
>>>
>>> 5 +
  File "<stdin>", line 1
    5 +
       ^
SyntaxError: invalid syntax
>>> 42 + 5 + * 2
  File "<stdin>", line 1
    42 + 5 + * 2
             ^
SyntaxError: invalid syntax
>>>
```

If you type a bad instruction python responds with an error message.


# The integer, floating point and string data types

Expression = values combined with operators (It always evaluate down to a single value)

Data type is category for values and every value belongs to exactly one data type.

Common Data types
- Integers
-  Floating-point numbers
-  Strings
  
```
>>> 'Hello World!
  File "<stdin>", line 1
    'Hello World!
    ^
SyntaxError: unterminated string literal (detected at line 1)        -----------> If you get this error probably you forgot the last '
>>> 'Hello World!'
'Hello World!'
```

# String Concatenation and Replication

The meaning of operator may change based on data types of the values next to it.

```
>>> 'Bhanu' + 'Malhotra' 
'BhanuMalhotra'

>>> 'Bhanu'+ 1 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str

>>> 'Bhanu' * 5                 -------> String Replication
'BhanuBhanuBhanuBhanuBhanu'
>>>

Doesn't make sense:

>>> 'Bhanu' * 5.0
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can't multiply sequence by non-int of type 'float'
>>> 'Bhanu' * 'Malhotra' 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can't multiply sequence by non-int of type 'str'
>>>
```

# Storing a value in Variables
If you want to use the result of an evaluated expression later in your program, you can save it inside a variable.
When a variable is assigned a new value, the old value is forgotten.
  
assignment statements:
```
>>> api_url= 'xyz.com'
>>> api_url
'xyz.com'


>>> api_url= 'xyz.com'
>>> api_url
'xyz.com'
```

# Variable Names
Invalid 
- hyphens are not allowed
- spaces are not allowed
- can't begin with a number
- can't be a number
- special characters like $ are not allowed
- special characters like ' are not allowed

Variables are case sensitive SPAM and spam are different variables. It is a python convention to start variable with lower case.

camlecase - lookLikeThis
underscores - look_like_this

A good variable name describes the data it contains.


# First Program


```py
#this program says hello and asks for my name
print('Hello World')
print('What is your name?') # ask for their name
myName=input()
print('It is a good to meet you,' + myName)
print('The length of your name is:')
print(len(myName))
```

```
$ python firstprogram.py 
Hello World
What is your name?
Bhanu
It is a good to meet you,Bhanu
The length of your name is:
5
```


```py
#this program says hello and asks for my name
print('What is your age?')
myAge=input()
print('You will be ' + str(int(myAge)+1) + '' +' in a year.')
```

```
$ python firstprogram.py 
What is your age?
1
You will be 2 in a year.
```


print is a function, string value passed to it is a argument.

You can also use print() to give an empty line.

input() function waits for the user to type some text on the keyboard and press enter.

len() function evaluates to the integer value of the number of characters in that string.

# The str(), int() and float() functions.

```py
$ python
Python 3.12.2 (tags/v3.12.2:6abddd9, Feb  6 2024, 21:26:36) [MSC v.1937 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> str(0) 
'0'
>>> 0
0
>>> str(0)
'0'
>>> '-99' 
'-99'
>>> int('-99') 
-99
>>> '3.14' 
'3.14'
>>> float('3.14') 
3.14
>>>
```

input() function always returns a string

```py
>>> spam = input()
55
>>> spam
'55'
to use it mathematicaly further
>>> spam = int(spam) 
>>> spam
55
```

If you pass any value to int it can't evaluate it will throw error.

```py

>>> int('99.9') 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '99.9'
```

If you need to round a floating number down

```py
>>> int(99.9) 
99
```


Integer can be equal to floating number
```py
>>> 42 == 42.00
True
>>> 42 = '42' 
  File "<stdin>", line 1
    42 = '42'
    ^^
SyntaxError: cannot assign to literal here. Maybe you meant '==' instead of '='?
>>>


-------------THE END-------------------------------
```
