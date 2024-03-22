# Lists

List data type and its cousin tuple

List and tuples can contain multiple values, which makes it easier to write programs that handle large amounts of data into hierarhical structures.

Lists can contain other list   

A list is a value that contains multiple values in an ordered sequence.

list value refers to list itself

A list value looks like this: ['cats', 'bat', 'rat', 'elephant']


```py
>>> [1, 2, 3]
[1, 2, 3]
>>> ['cats', 'bat', 'rat', 'elephant']
['cats', 'bat', 'rat', 'elephant']
>>> ['cats', 3.1415, True, None, 42]   
['cats', 3.1415, True, None, 42]
>>> spams = ['cats', 'bat', 'rat', 'elephant'] 
>>> spams
['cats', 'bat', 'rat', 'elephant']
>>>
```


#### spam variable is still assigned only one value

the value __[]__ is an empty list

### Getting individual values in a list with indexes

```py
>>> spams[0] 
'cats'
>>> spams[1] 
'bat'
>>> spams[2] 
'rat'
>>> spams[3] 
'elephant'
```


```py

>>> ['cats', 'bat', 'rat', 'elephant'][3] 
'elephant'

>>> 'Hello' + spams[0] 
'Hellocats'


>>> 'The ' + spams[1] + ' ate the ' + spams[0] + '.' 
'The bat ate the cats.'
>>>
```

### Python will give you an IndexError message if you use an index that exceeds the number of values in your list value.
```py
>>> spams[10] 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
### Indexes can be only integers not floats

```py
>>> spams[1.0] 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: list indices must be integers or slices, not float
```



List can also contain other list values


```py
>>> spams=[['hello','bye'],[121,131]]                

>>> spams[1]  
[121, 131]

>>> spams[0] 
['hello', 'bye']

>>> spams[0][1] 
'bye'
>>>
```

## Negative Indexes

```py
>>> spam = ['cats', 'bat', 'rat', 'elephant' ] 
>>> spam[-1] 
'elephant'
>>> spam[-2] 
'rat'
```

### Getting sublists with slices

spam[2] is a list with an index. (one integer)
spam[1:4] is a list with a slice. (two integers)

A slice will go upto, but will not include, the value at the second index.

```py
>>> spam[0:4]  
['cats', 'bat', 'rat', 'elephant']

>>> spam[0:3] 
['cats', 'bat', 'rat']

>>> spam[3:3] 
[]

>>> spam[2:3] 
['rat']

>>> spam[0:-1] 
['cats', 'bat', 'rat']

```


## Leaving out one or both of the indexes on either side of the colon in the slice

- Leaving out the first index is the same as using 0 or beginning of the list.
- Leaving out the second index is the same as using the length of the list

```py

>>> spam[2:]
['rat', 'elephant']

>>> spam[:3] 
['cats', 'bat', 'rat']

>>> spam[:]   
['cats', 'bat', 'rat', 'elephant']
```

### Getting a list's length with len()

```py
>>> spam[:]  
['cats', 'bat', 'rat', 'elephant']
>>> len(spam)
4
```

### Changing Values in a List with Indexes

```py
>>> spam      
['cats', 'bat', 'rat', 'elephant']

>>> spam[2] = 'mouse' 

>>> spam
['cats', 'bat', 'mouse', 'elephant']
```

```py
>>> spam[2] = spam[1] 

>>> spam
['cats', 'bat', 'bat', 'elephant']
```

```py
>>> spam[-1] = 'mouse' 

>>> spam
['cats', 'bat', 'bat', 'mouse']
>>>
```

### List Concatenation and List Replication

```py
# Concatenation
>>> [1,2,3,4] + ['one','two','three','four'] 
[1, 2, 3, 4, 'one', 'two', 'three', 'four']
```

```py
# Replication
>>> [1,2,3,4] * 3                   
[1, 2, 3, 4, 1, 2, 3, 4, 1, 2, 3, 4]
```

```py
>>> spam = [1,2,3,4]
>>> spam = spam + ['one','two','three','four'] 
>>> spam
[1, 2, 3, 4, 'one', 'two', 'three', 'four']
```

### Removing Values from Lists with del Statements


```py
>>> spam
[1, 2, 3, 4, 'one', 'two', 'three', 'four']
>>> del spam[4:] 
>>> spam
[1, 2, 3, 4]
```

Can also be used to delete a simple variable (unassignment)
```py
>>> del spam
>>> spam     
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'spam' is not defined
```

### Working with Lists

Instead of using multiple, repetative values, we can use a single variable that contains a list of variables.


```py
catNames = []
while True:
    print('Enter the name of cat ' + str(len(catNames) +1) + ' (Or enter nothing to stop.):')
    name = input()
    if name == '':
        break
    catNames = catNames + [name] 
print('The cat names are:')
for name in catNames:
    print(' ' + name)
```
```
python p.py
Enter the name of cat 1 (Or enter nothing to stop.):
zuppie
Enter the name of cat 2 (Or enter nothing to stop.):
blingo
Enter the name of cat 3 (Or enter nothing to stop.):
cow
Enter the name of cat 4 (Or enter nothing to stop.):
thinkpad
Enter the name of cat 5 (Or enter nothing to stop.):

The cat names are:
 zuppie
 blingo
 cow
 thinkpad
```

## Using for loop with Lists

```py
>>> for i in range(4):
...   print(i) 
...
0
1
2
3
```

```py
>>> for i in [0,1,2,3]:
...   print(i) 
...
0
1
2
3
```

What the previous loop actually does is loop through its clause with the variable i set to successive  value in the [0,1,2,3] list in each iteration.

#### A common Python technique is to use range(len(someList)) with a for loop to iterate over the indexes of a list.

```py
supplies = ['pencil', 'staplers', 'binders']
for i in range(len(supplies)):
    print('Index ' + str(i) + ' in supplies is ' + supplies[i])
    
```

```
python p.py
Index 0 in supplies is pencil
Index 1 in supplies is staplers
Index 2 in supplies is binders
```

### The in and not in Operators

You can determine whether a value is or isn't in a list with the in and not in operators.

```py
if 'howdy' in ['hello','buffalo','hi', 'howdy']:
    print('yes it is True')
```

```py
if 'howdy' not in ['hello','buffalo','hi']:
    print('yes it is True')
```

```
python p.py
yes it is True
```

```py
myPets = ['selfie', 'zoopie', 'neomi']
print('Enter a pet name:')
name = input()
if name not in myPets:
    print('I do not have a pet named ' + name)
else:
    print(name + ' is my')
```

```
 python p.py
Enter a pet name:
selfie
selfie is my
```

```
python p.py
Enter a pet name:
kikashi
I do not have a pet named kikashi
```


## The Multiple Assignment Trick

It is a shortcut that lets you assign multiple variables with the values in a list in one line of code.

The number of variables and the length of the list must be exactly equal.

```py
cat = ['fat', 'black', 'loud']
size, color, disposition = cat


print(size)
print(color)
print(disposition)
```

```
python p.py
fat
black
loud
```

## Augmented Assignment Operators

When assigning the value to a variable, you will frequently use the variable itself.

```py
>>> spam = 42
>>> spam = spam +2
>>> spam           
44
```

```
Augmented assignment statement                Equivalent assignment statement

spam = spam + 1                               spam += 1
spam = spam - 1                               spam -= 1
spam = spam * 1                               spam *= 1
spam = spam / 1                               spam /= 1
spam = spam % 1                               spam %= 1
```


The += operator can also do string and list concatenation
The *= can do string and list replication

```py
>>> spam = 'Hello' 
>>> spam += ' world!' 
>>> spam
'Hello world!'
```

```py
>>> spam *= 3
>>> spam
'Hello world!Hello world!Hello world!'
>>>
```

## Methods

A method is same thing as a function, except it is "called on" a value.

Each data type has its own set of methods

### Finding a Value in a List with index() Method

```py
>>> spam = ['hello','hi','ding','dong'] 

>>> spam.index('hi') 
1
```

When there are more than one occurence of a value in the list, the index of its first appearance is returned.

```py
>>> spam = ['hello','hi','ding','dong', 'ding'] 
>>> spam.index('ding') 
2
```

### Adding values to Lists with append() and insert() Methods

```py
>>> spam.append('moose') 
>>> spam      
['hello', 'hi', 'ding', 'dong', 'ding', 'moose']
```

```py
>>> spam      
['hello', 'hi', 'ding', 'dong', 'ding', 'moose']
>>> spam.insert(0,'good morning') 
>>> spam
['good morning', 'hello', 'hi', 'ding', 'dong', 'ding', 'moose']
```

Carefuly notice here one thing we are __NOT__ using:

- spam = spam.insert(0,'good morning') 
- spam = spam.append('moose')

We are only using:
- spam.insert(0,'good morning') 
- spam.append('moose')

Why?

Return value of both insert and append is none


append and insert are only for lists data type
```py
>>> cat = 'morning'
>>> cat.append('panchi') 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'str' object has no attribute 'append'
``` 

```py
>>> cat.insert(1, 'panchi') 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'str' object has no attribute 'insert'
```

### Removing values from Lists with remove()

```py
>>> spam
['good morning', 'hello', 'hi', 'ding', 'dong', 'ding', 'moose']
>>> spam.remove('good morning') 
>>> spam
['hello', 'hi', 'ding', 'dong', 'ding', 'moose']
```


If values appear multiple times in a list, only the first instance of the value will be removed.

```py
>>> spam
['hello', 'hi', 'ding', 'dong', 'ding', 'moose']
>>> spam.remove('ding')         
>>> spam
['hello', 'hi', 'dong', 'ding', 'moose']
```

__del__ statement is good when you know the index of the value you want to remove from the list.
__remove()__ method is good when you know the value you want to remove from the list.


### Sorting the values in a List with the sort() Method.

- sort() method sorts the list in place; don't try to capture the return value by writing code like spam = spam.sort()
- Can't sort lists which have both number and string values in them.
- 

```py
>>> spam = [2, 3, 3.14, -1, -3] 
>>> spam.sort()
>>> spam
[-3, -1, 2, 3, 3.14]

>>> spam = ['a',' d', 'y', 'c', 'f', 'k',' b'] 
>>> spam.sort()
>>> spam
[' b', ' d', 'a', 'c', 'f', 'k', 'y']
>>>
```

```py
>>> spam.sort(reverse=True) 
>>> spam
['y', 'k', 'f', 'c', 'a', ' d', ' b']
```


ASCIIbetical order: Upper case letters come before lower case.

```py
>>> spam = ['a','D', 'y', 'C', 'f', 'K','b']   
>>> spam.sort()
>>> spam
['C', 'D', 'K', 'a', 'b', 'f', 'y']
```

If you need to sort the values in regular alphabetical order, pass str.lower for the key keyword argument in the sort() method call.

```py
>>> spam = ['a','D', 'y', 'C', 'f', 'K','b']   
>>> spam.sort(key=str.lower)
>>> spam
['a', 'b', 'C', 'D', 'f', 'K', 'y']
>>>
```

### Example Program: Magic 8 Ball with a List

```py
import random

messages = ['It is certain',
            'It is decidedly so',
            'Yes definitely',
            'Reply hazy try again',
            'Ask again later',
            'Concentrate and ask again',
            'My reply is No',
            'Outlook not so good',
            'Very doubtful']
print(messages[random.randint(0, len(messages) -1)])
```

```
python p.py
Outlook not so good

python p.py
Outlook not so good

python p.py
Reply hazy try again

python p.py
My reply is No
```

## List like types: Strings and Tuples

- Lists are not the only data types that represent ordered sequences of values.
- Strings and lists are actually similar, if you consider a string to be a "list" of single text characters.

Many of the things you can do with lists can also be done with strings:
- indexing
- slicing
- using them for loops
- with len()
- in and not in operators


```py
>>> name = 'Bhanu' 
>>> name[0]
'B'


>>> name[-1] 
'u'


>>> name[0:3] 
'Bha'


>>> 'Bh' in name
True


>>> 'bh' in name 
False


>>> 'bh' not in name 
True


>>> for i in name: 
...   print('***' + i + '***')
...
***B***
***h***
***a***
***n***
***u***
>>>
```


## Mutable and Immutable Data Types

List is mutable - It can have values added, removed, or changed. 

String is immutable - It cannot be changed

```py

# can't change a character in a string 

>>> name = 'you are a cat' 
>>> name[4] = 'the' 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment


# Way to mutate a string   

>>> name = 'you are a cat' 
>>> name = name[0:7] + ' not ' + name[8:] 
>>> name
'you are not a cat'
>>>
```


#### Even though list value is mutable, the following code does not modify the list eggs:

```py
>>> eggs = [1, 2, 3] 
>>> eggs = [4, 5, 6] 
>>> eggs
[4, 5, 6]

```

Here an entirely new and different list value([4, 5, 6]) is overwriting the list value ([1, 2, 3]).

If we want to actually modify the original list in eggs to contain [4, 5, 6] you will need to do the following.

```py
>>> eggs = [1, 2, 3] 
>>> del eggs[0]
>>> del eggs[1] 
>>> del eggs[2] 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list assignment index out of range
>>> eggs            
[2]
>>> del eggs[0] 
>>> eggs        
[]
>>> eggs.append(4)  
>>> eggs.append(5)  
>>> eggs.append(6)  
>>> eggs        
[4, 5, 6]
>>>
```

This way the variable isn't changed.


## The Tuple Data Type

- Identical to list
- Different in 2 ways:
    - It is typed using () and not [].
    - Tuple Data type is immutable(can't be changed) whereas list is mutable.

```py
>>> eggs = (1, 3, 'hello', '5.23') 

>>> eggs[0] 
1

>>> eggs[2:4] 
('hello', '5.23')
```

```py
>>> eggs
(1, 3, 'hello', '5.23')
>>> eggs[2]= 99
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

If in case you have only one value in your tuple, you need to indicate this by placing a trailing comma after the value inside the parantheses.

```py
>>> type(('hello',)) 
<class 'tuple'>
>>> type(('hello'))  
<class 'str'>
```

Benefits of tuple 
- You can use tuples to convey to the reader of your code that you don't intend for that squence of values to change.

### Converting Types with list() and tuple() Functions

Page 97