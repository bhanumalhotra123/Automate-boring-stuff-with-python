# Dictionaries and structuring data

## The Dictionary Data Type

- Unlike inedexes for lists, indexes for dictionaries can use many different data types, not just integers.
-  Indexes for dictionaries are called keys, and a key with its associated value is called key-value pair.
- In code, dictionary  is typed with braces, {} 


```py
>>> myCat = {'size': '10', 'color': 'red' }      

>>> myCat['size']  
'10'
```

```py
>>> spam = {12333:'luggage1',13243:'luggage2', 23221:'luggage3'} 
>>> spam[12333] 
'luggage1'
```


## Dictionaries vs Lists

- Unlike lists, items in dictionaries are unordered.
- Why? Cause the index in dictionaries is something you set whereas in lists it is always 0,1,2.....


```py
>>> kiwi = ['a','b','c'] 
>>> mango = ['c','a','b'] 
>>> kiwi == mango
False
```

```py
>>> spam = {12333:'luggage1',13243:'luggage2', 23221:'luggage3'}
>>> potato = {12333:'luggage1',23221:'luggage3', 13243:'luggage2'} 
>>> spam == potato
True
```

#### Dictionaries can't be sliced as they are not ordered.

Even though dictionaries are not ordered, option to have arbitrary values for the keys allows you to organize your data in powerful ways.

Example:

```py
birthdays = {'kid1': 'jan1', 'kid2':'feb1', 'kid3':'mar1', 'kid4':'april1'}

while True:
    print('Enter a name: (blank to quit)')
    name = input()
    if name == '':
        break

    if name in birthdays:
        print(birthdays[name] + ' is the birthday of ' + name)
    else: 
        print('I do not have birthday information for ' + name)
        print('What is their birthday?')
        birthday = input()
        birthdays[name] = birthday
        print('Birthday database updated.')    

```

```
python p.py
Enter a name: (blank to quit)
kid1
jan1 is the birthday of kid1
Enter a name: (blank to quit)
kid2
feb1 is the birthday of kid2
Enter a name: (blank to quit)
kid3
mar1 is the birthday of kid3
Enter a name: (blank to quit)
kid4
april1 is the birthday of kid4
Enter a name: (blank to quit)
kid5
I do not have birthday information for kid5
What is their birthday?
may1
Birthday database updated.
Enter a name: (blank to quit)
kid5
may1 is the birthday of kid5
Enter a name: (blank to quit)
```


## The keys(), values(), items() Methods.

3 dictionary methods that will return list-like values of dictionary keys, values or both keys and values.

- The values returned by these methods are not true lists.
- They can't be modified and do not have an append() method.

```py

>>> spam
{'kid1': 'jan1', 'kid2': 'feb1', 'kid3': 'mar1'}

>>> for v in spam.values(): 
...   print(v) 
... 
jan1
feb1
mar1
>>>
```

```py
>>> for v in spam.keys():   
...   print(v) 
...
kid1
kid2
kid3
```

```py
>>> for i in spam.items():
...   print(i) 
...
('kid1', 'jan1')   #notice here values returned by the items
('kid2', 'feb1')
('kid3', 'mar1')
>>>
```

If you want a true list from one of these methods, pass its list-like return value to the list() function.

```py
>>> spam = {'kid1':'jan1','kid2':'feb1','kid3':'mar1'}
>>> spam.keys()
dict_keys(['kid1', 'kid2', 'kid3'])
>>> list(spam.keys()) 
['kid1', 'kid2', 'kid3']
```


Multiple assignment trick in a for loop to assign the key and value to seperate variables.

```py
>>> for k, v in spam.items():
...   print('Key: ' + str(k) + ' Value: ' + str(v)) 
...
Key: kid1 Value: jan1
Key: kid2 Value: feb1
Key: kid3 Value: mar1
```

### Checking Whether a Key or Value exists in a Dictionary

```py
>>> spam = {'kid1':'jan1','kid2':'feb1','kid3':'mar1'}
>>> 'name' in spam.keys()
False
>>> 'kid4' in spam.keys() 
False
>>> 'kid3' in spam.keys() 
True

>>> 'mar1' in spam.values() 
True
>>> 'mar3' in spam.values() 
False
>>>

```


## The get() Method

- It is tedious to check wether a key exists in a dictionary before accessing that key's value.

- Dictionaries have a get() method that takes two arguments: key of the value and a fallback value to return if the key don't exist.

```py
>>> picnicItems = {'apples': 5, 'bananas': 3, 'mangoes': 1} 
>>> 'I am bringing ' + str(picnicItems.get('mangoes', 0)) + ' mangoes' 
'I am bringing 1 mangoes'
```

```py
>>> 'I am bringing ' + str(picnicItems.get('pickle','noooo' )) + ' pickles' 
'I am bringing noooo pickles'
```

Without using get method python will cause an error:

```py
>>> 'I am bringing ' + str(picnicItems['pickle']) + ' pickles'     
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'pickle'
```

## The setdefault

If in case the key is not present in the dictionary, you have to add it by the following way:


```py
>>> spam = {'kid1':'jan1','kid2':'feb1','kid3':'mar1'}                      
>>> if 'kid4' not in spam:
...   spam['kid4'] = 'apr1' 

>>> spam
{'kid1': 'jan1', 'kid2': 'feb1', 'kid3': 'mar1', 'kid4': 'apr1'}
```




But setdefault() method gives you a way to do this in 1 line of code:




```py
>>> spam.setdefault('kid5','may1') 
'may1'
>>> spam
{'kid1': 'jan1', 'kid2': 'feb1', 'kid3': 'mar1', 'kid4': 'apr1', 'kid5': 'may1'}
```



The setdefault() method is a nice shortcut to ensure that a key exists.
```py
message = 'It was a bright cold day in April1, and the clocks were striking thirteen.'
count = {}   
                    
for character in message:        
    count.setdefault(character, 0)
    count[character] = count[character]+ 1

print(count)
```

```
python p.py
{'I': 1, 't': 6, ' ': 13, 'w': 2, 'a': 4, 's': 3, 'b': 1, 'r': 5, 'i': 6, 'g': 2, 'h': 3, 'c': 3, 'o': 2, 'l': 3, 'd': 3, 'y': 1, 'n': 4, 'A': 1, 'p': 1, '1': 1, ',': 1, 'e': 5, 'k': 2, '.': 1}
```

Here's a brief list of steps:

Initialize an empty dictionary called count to store character counts.
Iterate through each character in the message string.
For each character:
    Check if it exists as a key in the count dictionary using setdefault().
    If the character doesn't exist, set its count to 0.
Increment the count of the character by 1.
Print the count dictionary containing the character counts.



## Pretty Printing

It is more useful when using nested dictionaries

pprint() and pformat() will preety print a dictionary's values

```py
import pprint

message = 'It was a bright hot day in April, and the clocks were striking thirteen.'

count = {}

for character in message:
    count.setdefault(character, 0)
    count[character] = count[character] + 1
pprint.pprint(count)
```

```
python p.py       
{' ': 13,
 ',': 1,
 '.': 1,
 'A': 1,
 'I': 1,
 'a': 4,
 'b': 1,
 'c': 2,
 'd': 2,
 'e': 5,
 'g': 2,
 'h': 4,
 'i': 6,
 'k': 2,
 'l': 2,
 'n': 4,
 'o': 2,
 'p': 1,
 'r': 5,
 's': 3,
 't': 7,
 'w': 2,
 'y': 1}

```

pprint.pprint(count)
print(pprint.pformat(count))

these to are same



## Using Data Structures to Model Real-World Things

### A Tic-Tac-Toe Board

```py
theBoard = {'top-L':' ', 'top-M': ' ', 'top-R': ' ',
            'mid-L':' ','mid-M':' ','mid-R':' ',
            'low-L':' ','low-M':' ','low-R':' '}


def printBoard(board):
    print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R']  )
    print('-+-+-')
    print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R']  )
    print('-+-+-')
    print(board['top-L'] + '|' + board['top-M'] + '|' + board['top-R']  )

printBoard(theBoard)
```

```py
python p.py
 | | 
-+-+-
 | |
-+-+-
 | |
```

