
# Functions

### What we already know
- basic data types (ints, floats, strings)
- Some functions and methods to manipulate these data types (i.e. type(), len(), str.upper())
- where to put our data
    - one piece of data within a variable
    - multiple pieces of data within a list
- and how to manipulate and build these variables and lists
- Use conditional statements to allow the computer to choose when to execute certain commands
- use loops so that the computer can repeat tasks


### Learning Objectives
- Define a function that takes parameters.
- Return a value from a function.
- Test and debug a function.
- Set default values for function parameters.
- Explain why we should divide programs into small, single-purpose functions.



Imagine now that you're writing a piece of code...and you're writing up the exact same `if` statements, and the same loops, in multiple areas inside your program.

Instead of doing this, what we can do is make our own **functions** - where we can define our own command that performs the actions that we want it to. 

We've already encountered functions before - list.sort(), for example, is a function that takes your list, reorders the data inside it, and then gives it back to you.

Similarly, type() is a function that takes the data that you give it, tests which data type it is, and then prints out a statement that tells you what it is.

We can make a function using the `def`, or "definition" command, followed by what we would like our function to be called.

For example:


```python
def functionName(): #we also need these bracket on 
                    #the end
    print("let's make some code")
```


```python
# I can then run this code inside the function by "calling" the function
functionName()
```


```python

```


```python

```

We can also make it so that our function has to take some *parameters* when we call it.

Parameters are variables that we use inside the function while writing our code. For example, if I were to make a function that adds two numbers:


```python
def add(x,y):
    z = x + y
    print(z)
    
```


```python
add(2,3)
```


```python
# but it also works in situations we didn't expect - oops!

```

x and y would be the variables that I use inside the function, and are thus the *parameters* of the `add()` function.

However, if your function uses parameters, when calling your function you have to include data that could represent those parameters. Try calling `add()` below without any numbers


```python
# if we try to use this without parameters...
add()
```


```python
#but if I include two numbers inside it, add will work
add(2,3)
add(1,2)
```


```python
# what if I define a "z" outside of the function though?
x = 1
y = 4
z = 20

print("Add(1,4) makes z:")
add(x,y)


print("but z is still", z )

```

This is because the parameter names that we define inside the function **only exist inside the function**

If I make a new variable inside add, for example, that variable **will not exist outside of that function**


```python
def add2(x,y):
    new = x + y
    print(new)
```


```python
add2(1,2)

print(new)
```


```python
# But what if we try to assign our added value to a variable?
temp = add2(1,2) # will still 'print' 3

print(temp)

```

Why?


Well, so far add2 is only performing some math inside itself. It's not actually giving you back any data.

To do this, we have to tell the function what data to give back when we run it. We can do this with a `return` statement


```python
def add2(x,y):
    z = x + y
    return(z) #This means that our function is now GIVING BACK a value when we run it
```


```python
temp = add2(1,4)

temp
```


```python

```

We can only use return to give us back *one* item though. This means that if we need to return multiple values for our function, we need to store them inside another data type (like a list!)


```python

```


```python
def numCheck(x,y):
    numList = []



```


```python

```


```python
temp = numCheck(30,50)

temp
```

As you can see, this doesn't change the fact that "numList", as a variable, only exists within that function. However the *value* of numList, is now being given back to us and can be assigned to a variable.

#### A Challenge in Multiple Parts

#### Part 1

Now let's try to write a function that converts temperatures from Fahrenheit to Kelvin, and run it on a couple of different temperatures.

The math involved in this is:
`(temperature - 32) * (5/9) + 273.15`




Write the function fahr_to_kelvin that successfully gives you the value 273.15 when we give it a temperature of 32.


```python

```


```python

```

#### Part 2

Now that we've seen how to turn Fahrenheit into Kelvin, it's easy to turn Kelvin into Celsius - just take the temperature and minus 273.15

celsius = `kelvinTemperature - 273.15`


```python

```


```python

```

What if we then want to turn fahrenheit into celsius?

We could write out the math for the whole thing...but we already have some functions that do that for us!

A cool thing about making a function is that we can actually use a function inside another function.

If you think about it, we already are. In our numCheck function earlier, we were using `append()` - a list function - to add new values into a list.

#### Part 3

Write a function that takes a temperature in fahrenheit, and outputs a temperature in celsius.


```python

```


```python

```


```python

```

### Function Defaults

When you are defining your functions, you can actually set your parameters to have default values. 

You can do this by making your parameter '=' to something inside your function definition.


```python
def HelloWorld(message, times = 1):
    print (message * times)
```


```python
HelloWorld("Hello World ")
```

But! Order is important! What happens if you try to put times (with a default value) before message?


```python
def HelloWorld(times = 1, message):
    print (message * times)
```

The reasons for this are actually due to how Python processes parameters inside your functions.

In some languages, if you want to use parameters inside your function, you actually have to define them by name when you run it, you can't just put in the values


```python
def HelloWorld(message, times = 1):
    print (message * times)

HelloWorld(message = "Hello World ", times = 4)
```

In Python however, you just need to type in the values itself, and Python will take the values you put in and assign them to your parameters *in order*.


```python
HelloWorld("Hello World ", 4)
```


```python
HelloWorld(4,"Hello World ")
```


```python
def HelloWorld(message, times = 1):
    print(type(times))
    print(type(message))
    print (message * times)

HelloWorld(4,"Hello World ")
```

So, for example, with our HelloWorld function, if we were to define it with the times parameter first, if we tried to run `HelloWorld("Hello World ")`, it would assign "Hello World " to the `times` parameter, instead of `message`.

As message **doesn't** have a default value, this means that our function would fail and give us a nasty error.

To protect you from doing that, Python forces you to define functions with your *compulsory* parameters first, and you can put your default values after those. 

#### Challenge

Define a function, `stringCheck()`, that can accept two strings, and prints the longest string. 

But! I also want you to use another parameter, called `print_both`. If `print_both` is `True`, then if your strings are the same length it will print both of them. Otherwise, it will only print the first one. Give `print_both` a default value of `True`


```python

```


```python

```


```python

```


```python

```

## User Input

You can also program your code so that it can prompt a user for input.

Imagine, for example, programming your `HelloWorld` function to ask the user how many times they want to print the message. Or even what the message is.

To program a user input, you simply need to do:

```python

variableName = input()
```

You can also choose to include a message that displays when prompting the user, like this:

```python

variableName = input("This will display a message:")
```


```python
variable
```


```python

```

HOWEVER! For those using Python 2.x, you should use the raw_input() function, NOT input().

In Python 3, input() will automatically convert the user input into a string type. In Python 2, this function will actually evaluate what the user types in. This might not seem like an issue, but it can cause **massive** security holes in your program. Imagine if someone malicious typed in a command to exit python, and then had access to your local machine? Or a database beneath that?

By converting the user input into a string, you are "sanitising" the user input. Python 2's raw_input, and Python 3's input() do this automatically.


![image.png](attachment:image.png)
*"Exploits of a Mom", XKCD*

#### Mini Challenge

Make another function called HelloWorld, which prints the phrase "Hello World!", on separate lines, for as many times as the user tells it to.


```python

```


```python

```

### Challenge

Create a randomly generated list, with a length between 10 and 100, specified by user input.

Then, write a function that takes that list, and returns a new, sorted list that only contains unique values


```python
import numpy


# your list
listing = []


# the length of your list - make this a user input!
length = 

# This is randomly creating your list - don't change this!
for i in range(int(length)):
    listing.append(numpy.random.randint(0,9))
    



# Your unique/sorting function - you have to make this yourself!
def uniqueList(var):



    
    
    
    
#Running your functions
print("Sample list:", listing)
print("New list:",uniqueList(listing))
```


```python

```
