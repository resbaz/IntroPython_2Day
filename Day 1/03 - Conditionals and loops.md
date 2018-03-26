
# Conditionals

In this session we are going to learn how to program your computer to make choices about which action it should perform

### What we already know
- basic data types (ints, floats, strings)
- Some functions and methods to manipulate these data types (i.e. type(), len(), str.upper())
- where to put our data
    - one piece of data within a variable
    - multiple pieces of data within a list
- and how to manipulate and build these variables and lists

### Learning Objectives

- Write conditional statements including `if`, `elif`, and `else` branches
- Correctly evaluate expressions containing `and` and `or`
- Correctly write and interpret code containing nested conditionals
- Learn how to make the computer repeat instructions with loops


## What Are Conditionals?

Conditionals allow you make the computer or program perform a certain action depending on particular conditions.

But to assess a condition, we first need to understand how we can test them.

These tests are usually done using "equality operators". Things like:

- `<`, less than
- `>`, greater than
- `<=` less than or equal to
- `>=` greater than or equal to
- `==`, equals
- `!=`, does not equal
- `is`, `in` and `not`

Let's try using these in our cells


```python
# less/greater than

```


```python
#assigning the "none" value to the variable 'var'
var = None

# whereas double == is testing for equality
var == True
```


```python
# equal/not equal to

```


```python
# Can use in to test whether something exists in a data structure like a list
odds = [1,3,5,7]

```


```python
#we can use 'in' and 'not in; to check whether a value is in a list
print(1 in odds)
print('a' in odds)
```

    True
    False
    

#### Checking for Truth and Falsehood

These conditonal statements are returning True and False when you run this code. These just so happen to be another data type, **booleans**. These are the simplest ones, as they can only be `True` or `False`. You can also make variables have boolean values, and test those.


```python
#example
test = True

# Can test True/False in a few ways. Using ==, or is/not.
```


```python
test is True
```


```python
test is not True
```


```python
test == True
```

Now that we've got some basics down, let's try to use these inside something a bit more complicated

Take a situation like this for example - 

It's early morning. I wake up, and need to get ready for the day. What decisions should I make? What should I check before I leave?

Firstly, let's say that it's winter.


```python
winter = True
```

I can now use the function, `if`, to test something and then perform an action based on that.

**Plain Talk:**

If a condition is true, then do this action to this thing


** Python Talk**

```python
if condition:
    do this thing
   ```


```python
winter = False #this is a Boolean type. Booleans are True or False.

if winter == True:
    print("Turn on the heater")

print("Outside the if block")
```


```python

```


```python

```

However, this doesn't necessarily encompass all of the situations we want to perform an action for. What if we wanted to turn on the cooler if it wasn't winter?

This is where we use `else` statements - i.e. if your `if` condition isn't true, we perform the `else` action instead


```python
if winter == True:
    print("Turn on the heater")

else:
    print("Turn on the cooler")

print("Outside the if block")
```


```python

```

Often though, we need to test for multiple things inside a single `if` block. A single `if` isn't enough to cover all of the options and items we need to test! What if it's spring, and still quite warm? We probably wouldn't want to turn on the heater OR the cooler, right?


```python
season = "Spring"
if season == "Winter":
    print("Turn on the heater")

elif season is "Spring":
    print("Just make the goddamn coffee already")
    
else:
    print("Turn on the cooler")

print("Outside the if block")
```


```python

```


```python

```

But! You need to be careful of how your structure your if statements. Take the below example:


```python
# Where count is only ever 0 - 100
count = 20

if count < 100:
    print("Less than 100")

elif count < 50:
    print("Less than 50")

print("Outside the if block")
```


```python

```

We can also place conditional statements within a conditional statement. This is known as nesting.

``` python
if condition:
    if condition:
        do thing
```


```python
count = 20

if count < 100:
    print("Less than 100")
    
    if count < 50:
        print("Less than 50")

print("Outside the if block")
```


```python

```

You can also combine multiple conditions in a single line using the `and` or `or` statements, like so:

We can also use & instead of `and`, and `|` instead of `or`


```python
winter = False #this is a Boolean type. Booleans are True or False.
coffee = None


if (winter is True) or (coffee == None):
    print ("This is alright I guess")
    
elif (winter is True) & (coffee == None):
    print ("Kill everything")
```


```python

```


```python

```

#### Challenge

Together with your team mates, come up with your own morning routine. Try to use as many of the conditional testers as you can, without nesting more than 2-3 if statements.




```python

```


```python

```


```python

```


```python

```


```python

```

#### _Optional Challenge_

The bosses of a particular company recently evaluated their staff's salaries, and found that many weren't falling in line with the industry standard. To fix this, they decided that:

- all people earning below \$45,000 would get a 10% raise
- all people earning below \$60,000 would get a 5% raise
- all others would get a 2% raise


Your challenge now is to write a series of if, elif and else statements to adjust the employee salaries.



```python
from numpy import random

#This will randomly generate a number between 42000 and 130000
salary = random.randint(42000,130000)

print(salary)

```


```python

```


```python



```


```python

```

However they realised that after the adjustments, some people weren’t being paid appropriately. Someone who previously earned \$61,000 dollars would only get a 2% raise to \$62220, while someone who was earning \$60,000 would get a 5% raise to \$63000. 

To adjust for this, everyone with a salary between (inclusive):
- \$60,000 and \$62,000 will have their salary adjusted to \$63,000
- \$45,000 and \$48,000 will have their wage adjusted to \$50,000.

Edit your previous code to take these new adjustments into account


```python

```


```python

```

# For Loops - simplifying your code

#### Learning Objectives:

- Explain what a for loop does.
- Correctly write for loops to repeat simple calculations.
- Trace changes to a loop variable as the loop runs.
- Trace changes to other variables as they are updated by a for loop.




Suppose we want to print each character in the word "lead" on a line of its own. One way is to use four print statements:


```python
element = "lead"
print(element[0])
print(element[1])
print(element[2])
print(element[3])
```

But that's a bad approach. Firstly, you're doing a lot more typing than you need to, and it doesn't scale well. If you wanted to print every single letter in a sentence, or paragraph, you'd spend more time programming it than if you had just copied it out yourself. 

Secondly, if you were trying to automate something - so that it does something without you needing to be there every step of the way - this approach wouldn't work at all. Not every string, or list, or dictionary, is going to be the exact same size. You would need to program a new code every time you got new data.

Instead, we can use `for` loops. This is a function that lets us "iterate", or loop, over your strings and other data structures.

**Plain English Please:**

for each variable in a collection, perform an action on that variable

**Python Structure:**

The general structure of a `for` loop looks like this

```python
for variable in collection:
    do a thing
```


```python
# We can do this with both lists
```


```python
# and with strings! Any kind of "iterable" data type
```


```python

```

Note that a loop variable is just a variable that's being used to record progress in a loop. It still exists after the loop is over, and we can re-use variables previously defined as loop variables as well:


```python
name = "Kahli"
print(name)

# This is going to re-write "name"
for name in 'abc':
    print(name)

print('after the loop, name is', name)
```

### Combining loops and conditionals


#### Challenge

Given the list, veg = ['onion', 'potato', 'ginger', 'cucumber'], iterate over the list, but ONLY print out the first letter in the string. Unless the string is potato - then print out the whole thing


```python
veg = ['onion', 'potato', 'ginger', 'cucumber']
```


```python

```


```python

```

#### Challenge

Iterate through a given list of numbers. Add **odd** numbers to another list, called odd. Add **even** numbers to another list called even. Then, sort and print out both odd and even lists.

Hint: remember modulo, %?


```python
numberList = [1,4,3,6,5,9,8,2,7,10]

```


```python

```


```python

```


```python

```

### In Python, all objects are special, and one thing that makes a *list* special is because it is:

#### *Iterable*

 Which means we can use the for loop like we have been doing, thought what if we don't have a list (or something like it) and want to iterate over it?

### Range - the quick and dirty iterable for the hard working Pythoneer

Generally speaking, you can iterate, or loop, over most data types that act as collections or sequences. We are able to loop over the elements of strings because, inside Python, they are treated as a _sequence of letters_, just as a list is a _sequence of objects_. 

However, sometimes you want to loop over an object that it not naturally iterable, or you may even want to use the list (or string) **indexes** instead of the list item itself. 

e.g. where list = [1,2,3,4,5], I might only want to print out the elements 1, 2 and 3. Rather than programming an `if` statement like:


```python
listed = [1,2,3,4,5]

for num in listed:
    if (num == 1) or (num == 2) or (num == 3):
        print (num)

```

I can instead use the list indexes to get the data I want:


```python
for i in [1,2,3]:
    print(listed[i])
```

But! Rather than creating a list by hand every time you want to do something like that, you can use the `range()` function to create our own iterators for the values we specify.


```python
for num in range(3):
    print(listed[num])

```

`range()` works with anywhere between 1 to 3 "arguments", or options; start, stop and step. 


```python
# 1 value = range(stop)

```


```python
# if we look at this as a list we get:

```


```python
# 2 values = range(start, stop)

```


```python
#3 values = range(start, stop, step)

```

Inside a for loop, the iterator produced by `range()` works in much the same way as a list does.


```python
# now implement in for loop
for i in range(5, 16, 2):
    print (i)

list(range(5, 16, 2))
```

By combinging `range()` with our `len()` function, we've now got a convenient way to iterate over the length of our lists


```python
# from 0 to 3 (non inclusive)
odds = [1,3,5,7]

for i in range(len(odds)):
    print("index i =",i)
    print("odds at i =",odds[i])
```


```python
string = "This. Is. Python!"


```


```python

```


```python

```

** Pro tip, Range is the simple and most elegant iterable operator, but there are a whole heap of premade iterators that can make your life easier check it out at:**

https://docs.python.org/3.6/library/itertools.html

#### Challenge

In your groups (or individually), write a program which will find all such numbers which are divisible by 7 but are not a multiple of 5,
between 2000 and 3200 (both included).
The numbers obtained should be printed as a list.

*Hint: This will require to you combine range with some modulo conditions.*


```python

```


```python

```


```python

```

# While Loops

The while statement allows you to repeatedly execute a block of statements as long as a condition is true. A while statement can have an optional else clause.




```python
n = 0

while n < 10:
    print('n is less than ten')
    n+=1 # The same as n = n+1

```

While loops can be quite dangerous though - what happens if you choose a really bad stop condition?


```python
# Be prepared to press the stop button on this...

var = True
n = 0

while var == True:
    n += 1
    print(n)
```

**While loops are great when you don't actually know beforehand how many times you want to repeat you block of code To that end we are going to do an interesting challenge**

#### Challenge

Using while loops, write a program to print the even numbers between 0 and n, where n is a randomly generated integer.

Example:
If n = 10

Then, the output of the program should be:  
`
0  
2  
4  
6  
8  
10
`


```python
from numpy import random

num = random.randint(15,200)

print(num)

```

    190
    


```python

```


```python

```


```python

```


```python

```

#### Challenge

Write a `while` loop that takes a string, and produces a new string with the characters in reverse order, without using the `.reverse()` function:
i.e. 'Newton' becomes 'notweN'.


```python
#HINT
word = ""

word = "a" + word
print(word)
word = "b" + word
print(word)
```


```python
word = "Newton"


```


```python

```
