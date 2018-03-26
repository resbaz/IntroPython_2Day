
# New Data Type: Lists

### Learning Objectives

- To understand the basic structure of a list
- To know how to create, index and subset a list
- Learn the difference between mutable and immutable objects
- Adding and deleting list elements
    - Describe the difference between append(), insert(), del, remove() & pop()
- List functions


## Lists

A list allows you to store many different values, of many different data types, in the same structure. 

We can make a list by putting the values into square brackets, []



```python
#we can make empty lists
[]
```


```python
list()
```


```python
#Or lists with things inside them

```


```python
#To save this list though we need to assign it to a variable
tempList
```

### Indexing a list
Sometimes we only want to access certain *elements*, or data, inside a list. We can do by calling the list *index*, or the position of the data element, from inside the list


```python
tempList[1]
```

Wait, but that's given us the number 2? Why?

---

This is because Python actually works based on 0-indexing, meaning that it starts counting from 0 instead of 1. 

This means that if we want to get the first thing from inside of our list, we actually have to call list[0], instead of list[1]


```python
tempList = [1, 2.5, 3, "This", ["Lookie!","Another","List!"]]

print("0",tempList[0])
print("1",tempList[1])
print("2",tempList[2])
print("3",tempList[3])
print("4",tempList[4])
```

    0 1
    1 2.5
    2 3
    3 This
    4 ['Lookie!', 'Another', 'List!']
    

You can also use negative index numbers to start counting from the end of the list instead


```python
print('first and last:', tempList[0],"and", tempList[-1])
```

    first and last: 1 and ['Lookie!', 'Another', 'List!']
    

**_Interstingly, strings behave a lot like a list of letters..._**


```python
the_truth = "winter is coming"

the_truth[0]
```


```python

```

### Mutability

One of the properties of lists is that you can over-write data inside the list with new values. This means that lists are **_mutable_**, or changeable.

In contrast, strings are actually immutable. If you want to change something inside a string, you have to replace it with a whole new one.



```python
# What happens when we try to replace part of a string?
superhero = "superman"
superhero[0] = "S"

```


```python
# Try it with a list instead

heroes = ['s','u','p','e','r']

print("Old:",heroes[0])

heroes[0] = "Z"

print("New:", heroes[0])
```

    Old: s
    New: Z
    


```python

```

### Slicing

Slicing allows us to access *sections* of the list, instead of the whole thing, or only a single element.

Slicing can be used on a number of different python data types, including strings. This is because we can think of strings as being a _sequence_, or _list_ of letters.


```python
indexList = ["Index 0", "Index 1", "Index 2", "Index 3"]

print('Slicing 1:3 is', indexList[1:4])
```

When doing this you probably noticed that slicing is _non-inclusive_, meaning that in a slice from indexes 0-5, the "5" is not included. This is because sequencing in Python looks sort of like this:
![image.png](attachment:image.png)

That does mean that we can do stuff like this though, while slicing:


```python
print('Index 1 to 3 is', indexList[1:4]) 

# Whereas if we were to try and find index[4], it would be over the edge!
print(indexList[4])

```

We can also "auto-complete" our slicing by leaving the front or back of the slice open:


```python
print('Index 2 to end is', indexList[2:])
```


```python
print("Start UP TO index 2 is:", indexList[:2])
```


```python
#As well as do negative, or wrap-around slicing
print('Index 1 to -1 is', indexList[1:-1])
```


```python
#Or grab the whole thing
print('Index start to end is', indexList[:])
```


```python
# You can do the same thing on strings
stringExample = "Hello World!"

print(stringExample[:5])

```


```python
#You can also use slicing to quickly assign new values to a list
odds1 = [1,3,5,7]

#change index 1 -> 14, and index 2 -> 9
odds1[1:3] = [14,9] 

print(odds1)
```


```python

```

#### Mutability and Variable assignment

Say that you want to a copy the values inside a list into a different list, but then want to change one of them.

Because of the way that these two lists are stored within your computer's memory, if you just use variable assignment (e.g. list2 = list1), this can cause problems later on.


```python
odds1 = [1,3,5,7]
odds2 = odds1

print("Odds1:",odds1)
print("Odds2:", odds2)
```


```python
odds1[1] = 1300

print("Odds1:",odds1)
print("Odds2:", odds2)
```

Oh dear, that's not quite what we wanted. What would happen if we just copied everything inside the list instead?


```python
odds1 = [1,3,5,7]

odds2 = odds1[:] #So take everything from inside odds1

print(odds1)
print(odds2)
```

    [1, 3, 5, 7]
    [1, 3, 5, 7]
    


```python
odds1[3] = 1300
print(odds1)
print(odds2)
```

    [1, 3, 5, 1300]
    [1, 3, 5, 7]
    

#### Challenge

Given a string, `s`, of length at most 200 letters and a variety of integers, return the slice of this string from paired indices, inclusively. e.g. `a` through `b`, `c` through `d`, and `e` through `f`, etc. In other words, we should *include* the letters AT s[b] and s[d] in our slice. Make sure to include a space between each word. 
E.g.

`s = "HumptyDumptysatonawallHumptyDumptyhadagreatfallAlltheKingshorsesandalltheKingsmenCouldntputHumptyDumptytogetheragain"
a = 22; b = 27; c = 97; d = 102`

Would print:

`Humpty Dumpty`



```python
zen = "BeautifulisbetterthanuglySimpleisbetterthancomplexComplexisbetterthancomplicated"
#Pair 1
a = 50; b = 56
# Pair 2
c = 31; d = 32
# Pair 3
e = 21; f = 24
```


```python

```


```python

```


```python

```

## Adding and Deleting List Elements

Just creating our list isn't enough though - a lot of the time we need to be able to delete and add new elements into it as required. This can be used to record which items you've already seen when going through a spreadsheet, checking whether something belongs to a certain group, etc. We can do this with a few different methods.

### Append
To add new data into a list, we can use the `.append()` method. This adds the newest piece of information onto the *end* of the list.



```python
odds = [1,3,5,7]
```


```python
print("Odds before:", odds)
#list.append()
odds.append(9)

print("Odds after:", odds)
```

### Insert

`insert()` lets us put a new item into your list at the location of your choosing. 

The basic structure of this is *list.insert(__list index,new item__)*


```python
odds[2] = 4
```


```python
odds.insert(3,5)
print (odds)

```


```python
odds.insert(20,4)
print(odds)
```

### Deleting items

There are three options when deleting items from your list. 

The first is `del`, which removes the item at a specific index location and returns your modified list back to you. This works based on this kind of format, `del list[index]`


```python
odds = [1,3,4,5,7,8]
print(odds)
```


```python
del odds[-3]
print (odds)
```


```python
# But you can't go off the end: Error
del odds[12]
```

The second is `remove()`. Rather than deleting from a specific list index, `remove()` will find and delete the first matching *value* from your list, and return your modified list back to you.

It's typically used list this: `list.remove(variable)`


```python
odds = [1, 3, 4, 5, 4, 7, 9, 9]
```


```python
odds.remove(4)
print(odds)
```


```python
#If it doesn't exist though....Error
odds.remove(12)
```

Lastly we have `.pop()`. 

Like `del`, `pop()` is index based. However, while your list is still modified, `pop()` actually gives you back the value that you've removed. 


```python
odds
```


```python
temp = odds.pop(1)
```


```python
print("Odds before pop:",odds)

print(odds.pop(5))

print("Odds after pop:", odds)
```


```python
# Similarly to del...Error
odds.pop(10)
```

#### Challenge

So far, most of the elements that we have added to our collections have been string, float, or integer data types. However, lists can store practically any other data type, including another list. This process is called nesting and it is a bit like Russian dolls.


```python
pets = ['dogs', 'cats', 'fish']

pets.pop(0)   # Get rid of dogs
dog_breeds = ['bulldog', 'terrier', 'greyhound']
pets.append(dog_breeds)  # append list of dog breeds available

```

With your team mates, work out what this code does, and then how to return the string 'greyhound' from inside this list.

Hint: if you index a list like this, `list[0]`, and `type(list[0])` is a list, how might you pull out a value from inside this second list?


```python

```


```python

```


```python

```

### Other list functions: Our first googling exercise

Much like strings, there are many useful methods in the Backpack of the list:

https://docs.python.org/3/tutorial/datastructures.html

I will assign each group a method, and I want you guys to go to the link above, and figure out what that method does, and show me, give me an example



```python
list.sort()
```


```python
list.reverse()
```


```python
list.count()
```


```python
list.extend()
```


```python
list.clear()
```


```python

```


```python

```


```python

```

More information on `list.sort()`, and `list.reverse()`

`list.sort()` will sort your list based on "lexicographic order". This means that capital A-Z are sorted before lower-case a-z. 

However, sort() will not work if you have both strings and numeric data types in your list. It can only work if they are all strings, or all numeric (a combination of int and float).


```python
leads = []
```


```python
leads.sort()
print(leads)
```


```python
leads.append(3)
print("New names:", leads)
```


```python
#Doesn't work with a mixture of data types
leads.sort()
```


```python
# But is fine with both ints and floats

```

`reverse()` will take your list and reverse the order of the elements. 

So a list that was [1,2,3], would become [3,2,1]


```python
nums.reverse()
print(nums)
```


```python
#the list doesn't have to be sorted either
print(leads)

leads.reverse()

print(leads)

```


```python

```
