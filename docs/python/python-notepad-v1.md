---
layout: default
title: Python Note
parent: Python
---

Here I note down some of the topics of Python as my learning procedure. You are welcome to find any error and contribute.

# Topics

- [List](#list)
- [List Comprehension](#list-comprehension)
- [2D List](#2d-list)
- [Dictionary](#dictionary)
- [Functions](#functions)
- [Appendix](#appendix)

# List

Consider a list (list = []). You can perform the following commands:

- _insert i e_: Insert integer at position .
- _print_: Print the list.
- _remove e_: Delete the first occurrence of integer .
- _append e_: Insert integer at the end of the list.
- _sort_: Sort the list.
- _pop_: Pop the last element from the list.
- _reverse_: Reverse the list.

# List Comprehension

**Example 1**

From

```
numbers = [1, 2, 3, 4, 5]
doubled_odds = []
for n in numbers:
    if n % 2 == 1:
        doubled_odds.append(n * 2)

```

To this

```
numbers = [1, 2, 3, 4, 5]
doubled_odds = [n * 2 for n in numbers if n % 2 == 1]
#or
doubled_odds = [
    n * 2
    for n in numbers
    if n % 2 == 1
]
```

**Example 2**

```
>>> [(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)]
```

and it’s equivalent to:

```
>>> combs = []
>>> for x in [1,2,3]:
...     for y in [3,1,4]:
...         if x != y:
...             combs.append((x, y))
...
>>> combs
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)]
```

**Example 3**

S = {x² : x in {0 ... 9}}
V = (1, 2, 4, 8, ..., 2¹²)
M = {x | x in S and x even}

```
>>> S = [x**2 for x in range(10)]
>>> V = [2**i for i in range(13)]
>>> M = [x for x in S if x % 2 == 0]
>>>
>>> print S; print V; print M
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
[1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048, 4096]
[0, 4, 16, 36, 64]

```

**Example 4: Removing vowels from a sentence**

```language
def eg2_for(sentence):
    vowels = 'aeiou'
    filtered_list = []
    for l in sentence:
        if l not in vowels:
            filtered_list.append(l)
    return ''.join(filtered_list)

def eg2_lc(sentence):
    vowels = 'aeiou'
    return ''.join([ l for l in sentence if l not in vowels])
```

# 2D List

**Create a list**

elements = []

**Append empty lists in first two indexes**

elements.append([])
elements.append([])

**Add elements to empty lists**

elements[0].append(1)
elements[0].append(2)

elements[1].append(3)
elements[1].append(4)

**Display top-left element**

print(elements[0][0])

**Display entire list**

print(elements)

**Loop over rows**

```
for row in elements:
    # Loop over columns.
    for column in row:
        print(column, end="")
    print(end="\n")
```

**Output**

1

[[1, 2], [3, 4]]

12

34

##### To initialize a two-dimensional array in Python:

```
a = [[x for x in range(5)] for y in range(5)]
```

**Output**

[[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]

# Dictionary

A dictionary can be thought of as an unordered set of key: value pairs.

A pair of braces creates an empty dictionary: {}. Each element can maps to a certain value. An integer or string can be used for the index. Dictonaries do not have an order.

```language
dict = {}
dict['Ford'] = "Car"
dict['Python'] = "The Python Programming Language"
dict[2] = "This sentence is stored here."

print(dict['Ford'])
print(dict['Python'])
print(dict[2])
```

### Dictionary methods

_Python provides you several built-in methods for working with dictionaries._

- _popitem()_ Returns randomly select item from dictionary and also remove the selected item.
- _clear()_ Delete everything from dictionary
- _keys()_ Return keys in dictionary as tuples
- _values()_ Return values in dictionary as tuples
- _get(key)_ Return value of key, if key is not found it returns None, instead on throwing KeyError exception
- _pop(key)_ Remove the item from the dictionary, if key is not found KeyError will be thrown

```language

>>> friends = {'tom': '111-222-333', 'bob': '888-999-666', 'jerry': '666-33-111'}

>>> friends.popitem()
('tom', '111-222-333')

>>> friends.clear()

>>>  friends
{}

>>> friends = {'tom': '111-222-333', 'bob': '888-999-666', 'jerry': '666-33-111'}

>>> friends.keys()
dict_keys(['tom', 'bob', 'jerry'])

>>> friends.values()
dict_values(['111-222-333', '888-999-666', '666-33-111'])

>>> friends.get('tom')
'111-222-333'

>>> friends.get('mike', 'Not Exists')
'Not Exists'

>>> friends.pop('bob')
'888-999-666'

>>> friends
{'tom': '111-222-333', 'jerry': '666-33-111'}
```

**Using Functions to Access Elements**

In addition to using keys to access values, we can also work with some built-in functions:

- dict.keys() isolates keys
- dict.values() isolates values
- dict.items() returns items in a list format of (key, value) tuple pairs

**Comprehension**

```
squares = {x: x*x for x in range(6)}

# Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
print(squares)
```

# Functions

#### range()

_range([start], stop[, step])_

- start: Starting number of the sequence.
- stop: Generate numbers up to, but not including this number.
- step: Difference between each number in the sequence.

#### map()

The map(aFunction, aSequence) function applies a passed-in function to each item in an iterable object and returns a list containing all the function call results.

```language
>>> items = [1, 2, 3, 4, 5]
>>> def sqr(x): return x ** 2

>>> list(map(sqr, items))
[1, 4, 9, 16, 25]
```

#### map() with if else

```
list(map( lambda x: x.lower() if x.isupper() else x.upper(), i))
```

# Appendix

#### \_ :

It's just a variable name, and it's conventional in python to use \_ for throwaway variables. It just indicates that the loop variable isn't actually used.

#### list to string

The join function is a more flexible way for concatenating string. With join function, you can add any character into the string.

```
''.join(list)
```

#### string to list

Split strings is another function that can be applied in Python let see for string "guru99 career guru99". First here we will split the string by using the command word.split and get the result.

```
word="guru99 career guru99"
print word.split(' ')
```

The output will be ['guru99', 'career', 'guru99']
Another way:

```
>>> string = "abracadabra"
>>> l = list(string)
```

#### swap case

The method swapcase() returns a copy of the string in which all the case-based characters have had their case swapped.

```
str.swapcase();
```

#### Exponentiation:

(\*\*). This operator raises the number to its left to the power of the number to its right: for example 4\*\*2 will give 16.
