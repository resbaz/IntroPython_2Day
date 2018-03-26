
# New Data Type: Dictionaries

### What we already know
- basic data types (ints, floats, strings)
- Some functions and methods to manipulate these data types (i.e. type(), len(), str.upper())
- where to put our data
    - one piece of data within a variable
    - multiple pieces of data within a list
- and how to manipulate and build these variables and lists
- how to create our own, DIY custom functions

### Learning Objectives

- Understand the underlying structure of a dictionary
- Know how to access dictionary elements
- Adding and deleting dictionary elements
    - Describe the difference between del & pop()
- Be able to describe when a situation is best suited for a dictionary vs. a list
- Checking the existence of a key
- Iterating over a dictionary

## Dictionaries

Dictionaries are another kind of data type used by Python.

Remember our List:

|Index|Item|
|-----|-----|
|0|1|
|1|2.5|
|2|3|
|3|'This'|
|4|[]|

in which each item in a list is associated with an index number...

Well, in a dictionary, we essentially make our own indices!

|Key|Value|
|-----|-----|
|iphone|2005|
|iPhone Pod|3010|
|iphone3G|2004|
|iphone3GS|2009|
|iphone4|2010|
|iphone4S|2010|
|iphone 4SS|2015|

Rather than using an index, like a list, a dictionary uses "keys", typically strings or numbers, that you define. Each "key" of this dictionary is mapped to a value. (_Programming lingo: This is known as an associative array, or hash tables, for those who have programmed before_). 

Like a list, a dictionary can contain any kind of data type for it's values. 

Dictionaries consist of key-value-pairs, and as they can only be accessed using the 'key' names, they are unordered. 

You can make a dictionary by using `dict()`, or `{}`


```python
# An empty dictionary
dict()
{}
```

While the above makes an empty dictionary, sometimes you want to create one that already has values inside of it - like defining a list as [1,2,3,4].

We do this by using the {} brackets, and defining the names of a "key", and it's "value" at the same time, like so:


```python
# Live example




```


```python
# An example of a dictionary with keys and values

released = {    
    "iphone" : 2005,
    "iPhone Pod": 3010,
    "iphone3G" : str(2004),    
    "iphone3GS": str(2009),
    "iPhone Smart": 2001,
    "iphone4" : 2010,
    "iphone4S": '2010',
    'iPhone 4SS' : 2015
}

print(released)
```

The great thing about dictionaries is that, like lists, the data stored inside of them can be any kind of data type.

You can even store a dictionary inside a dictionary!

If you want actually access the value for a particular key in your dictionary, you can do so similar to how you do for a list - except instead of using a number to represent what 'index' your data is stored in, you use the key name instead


```python
# Accessing your dictionary
released['iphone']
```


```python

```

In addition, just like a list, dictionaries are mutable!


```python
# Dictionaries are mutable (they can be changed)

```


```python

```

### Adding and deleting from your dictionary

Adding to your dicitonary is simple - you just "call" your dictionary with a new key name, and assign it a value.



```python
# Adding new elements
released['temporary'] = "Temporary record"

released
```


```python

```

Similarly to how we delete items from lists, we can delete records from our dictionary using `.pop()` and `del`


```python
# Deleting elements
# same as lists, "pop" gives you the deleted element
released.pop("temporary")

```


```python
# While del removes the key and value from the dictionary. 
del released["iphone4S"]

```


```python

```

#### Challenge

Find the correct release dates for the iPhone models (google!), and change the dates currently inside the dictionary. In addition, add the newest iPhone model and release date, and delete any records that don't actually exist on the market (e.g. 'iPhone Smart')


```python
released
```


```python

```


```python

```


```python

```

#### Discussion Question
Which would you store the following data set as a List or a Dictionary?

    1.) output from a single datalogger
    2.) Coefficients and p values from a statistical test
    3.) metadata for a GIS file
    1.) temperature values from a network of data loggers
    

### What if we want to check the keys? Or see the values in our  dictionary?

**Our Special dictionary object has special methods to do that**

- `dict.keys()`
- `dict.values()`


```python
released.keys()
```


```python
released.values()
```

What this does is give you a list that contains all of the values contained within your dictionary. As this is a list, you can thus use in/not in just as you would with a list!


```python
'iphone' in released.keys()
```


```python
'2010' not in released.values()
```

#### Hack Tip: Checking if a Key Exists

As with a list, sometimes you need to check whether or not something exists within your dictionary. This could be so that you don't accidentally over-write it, or more commonly, to avoid being thrown an error if you try to access a key that doesn't exist

We can do this using the same kind of **'in'** and **'not in'** conditionals that we learned about previously


```python
temp_dict = {}
temp_dict["temp"] = "temporary record"
```


```python
# Check if there's a key called temp
'temp' in temp_dict
```


```python
# What if we tried to do the same with a value?
'temporary record' in temp_dict
```


```python

```

What we're seeing above is that Python is checking whether 'temp' is a **key** within our dictionary. If we want to check whether something exists amonst the **values**, we need to use the `dict.values()` function instead.


```python

```

### Iterating Over Dictionaries

Because dictionaries actually exist as key and value **pairs**, trying to loop over them in the same way that we would a list doesn't quite work:


```python
# dictionary
personal = 


```


```python
# This will only give me the keys!!
for item in personal:
    print(item)
```

If you want to access the values, or both the keys **and ** the values, you need to use specific commands


```python
# This will give us back a list, as expected, but with a twist
personal.items()
```


```python

```


```python
#You can also use .keys() to get just the keys


#And .values() to get just the values


```


```python

```


```python

```

####  Challenge

We want to create a dictionary that counts how many times a word occurs inside a list. For example, where

`sentence = ['list', 'of', 'words', 'list', "!"]`

The dictionary we should get back would be:

```python

counts = {'list' : 2, "of" : 1, "words": 1, "!": 1}
```

Within the code, we'd have to run through the words in the sentence, and increment the dictionary count for that word by 1 each time, like so:

` counts["of"] += 1`

In your group, try to iterate over the list `sentence`, defined below, to create your own `counts` dictionary. Output the word which occured the most amount of times.


```python
sentence = ['How', 'many', 'words', 'is', 'this', 'so', 'far', '?', "!", 'Too', 'many','I', "say", "!", 'Computer', 'science', 'has', 'gone', 'too', 'far', '!']

counts = {}




```


```python

```


```python

```

#### _Optional Challenge_

A robot moves in a plane starting from the original point (0,0). The robot can move toward UP, DOWN, LEFT and RIGHT with a given steps. The trace of robot movement is shown as the following:
UP 5
DOWN 3
LEFT 3
RIGHT 2

The numbers after the direction are steps. Please write a program to compute the distance from current position after a sequence of movement and original point. If the distance is a float, then just print the nearest integer.

Example:
If the following dictionary is given to the program - 

`directions = {"UP": 5, "DOWN": 3, "LEFT": 3, "RIGHT": 2}`

Then, the output of the program should be: 2

Hint: distance is computed as `round(math.sqrt(pos[1]**2+pos[0]**2))`

![image.png](attachment:image.png)


```python
from numpy import random

# pos[x axis, y axis]
pos = [0,0]

directions = {"UP": random.randint(0,10),
              "DOWN": random.randint(0,10),
              "LEFT": random.randint(0,10),
              "RIGHT": random.randint(0,10)}



```


```python

```


```python

```


```python

```
