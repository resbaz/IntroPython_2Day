
# Post-Day 1 Homework


## Question 1:

Write a program which accepts a sequence of comma-separated numbers as user input (code provided) and turns this into a sorted list which contains every number.

Suppose the following input is supplied to the program:  
  `34,67,55,33,12,98`

Then, the output should be:  
  `['12', '33', '34', '55', '67', '98']`


#### Background Information  

##### `input()`

When using `input()`, you, the coder, can enter your own values. If you press enter, you can then use whatever you input into the little dialog box as a `string`. You can also leave a little message to display next to the prompt, so that you know what kind of values you're looking for. 

Here's a short tutorial if you'd like to read more: https://www.python-course.eu/python3_input.php

##### `str.split()`  
This homework exercise is going to require you to do a little research of your own to complete. You can find some information about the string method `str.split()` at these websites - see if you can figure out how to use it for this problem! 
- http://www.pythonforbeginners.com/dictionary/python-split
- https://docs.python.org/2/library/stdtypes.html#str.split






Here's some code to get you started:


```python
# User Input - This should open a little box at the bottom where you can put in values
# Ive left this up as an example, try to run it again and see what happens!
string = input("Please enter a list of comma separated numbers: ")
```

    Please enter a list of comma separated numbers: 3,6,5,4,9,10,12



```python
print(string)
```

    3,6,5,4,9,10,12



```python

```


```python

```


```python

```

## Question 2


Write a Python program which accepts the user's first and last name and print them in reverse order with a space between them.

**Hint:** Remember how I used `input()` above? How could you do the same?


```python

```


```python

```


```python

```

## Question 3

Print the smallest number from a randomised list with 20 integers


```python
# Creating a randomised list
from numpy import random
unsorted = []
for i in range(20):
    unsorted.append(random.randint(1,1000))

# Your final list
print(unsorted)
```

    [98, 610, 621, 38, 646, 304, 10, 704, 714, 65, 964, 359, 774, 881, 186, 161, 166, 271, 527, 482]



```python

```


```python

```

## Question 4

Using this same list, `unsorted` as previously, print the largest number from this list


```python

```


```python

```


```python

```

## Question 5

Print a specified list after removing the 0th, 4th and 5th elements.

Sample List : `['Red', 'Green', 'White', 'Black', 'Pink', 'Yellow']`  
Expected Output : `['Green', 'White', 'Black']`  


```python
sampleList = ["How","Are","You","Having","Dinner","Time","Fun","Yet","?"]
```


```python

```


```python

```


```python

```


```python

```
