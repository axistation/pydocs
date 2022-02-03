---
sidebar_position: 5
---

# Functions
Perform actions on data.  We can create out own functions so that we don't need to write repetitive code.

## Define a function
The function is stored somewhere in memory after it is defined:
```python
def say_hello():
    print('hello')

say_hello() # hello
print(say_hello) # <function say_hello at 0x7ff809d46e10>
print(say_hello())
# hello
# None (function returns nothing)
```

## Arguments vs Parameters
Paramters are used when defining a function, whereas arguments are the values used when calling (or invoking) a function.
```python
# Parameters
def say_hello(name, emoji):
    print(f'hello {name} {emoji}')

# Arguments (positional)
say_hello('Andy', '😊') # hello Andy 😊
say_hello('Dan', '😊') # hello Dan 😊
say_hello('Emily', '😊') # hello Emily 😊
```

## Default Parameters and Keyword Arguments
Default parameters are used when no arguments are given when calling the function (more safe).  Keyword arguments allows to specify what value you are assigning to which argument irrespeictive of order.
```python
# default parameters (when no arguments are given when callling)
def say_hello(name='Darth Vader', emoji='😈'):
    print(f'hello {name} {emoji}')

sayhello() # hello Darth Vader 😈
sayhello('Timmy') # hello Timmy 😈

# keyword arguments
say_hello(name='Bibi', emoji='😊')
```
:::tip
It is good practice to follow the argument order as defined by parameter.  
It is easy to confuse default parameters with keyword arguments.
:::

## Return
As a rule of thumb, functions should do one thing really well, and should always return something.  If nothing is returned, it will return `None`.
```python
def sum(num1, num2):
    num1 + num2

print(sum(4,5)) # None

def sum(num1, num2):
    return num1 + num2

total = sum(4,5) # assign returned value to variable
print(total) # 9

# nested functions
def sum(num1, num2):
    def another_func(n1, n2):
        return n1 + n2
    return another_func(num1, num2)

total = sum(10, 20)
print(total) # 30
```
:::note
A `return` automatically exits the function.
:::

## Methods vs Functions
Methods are always owned by objects where as functions can be called on something.  Both perform actions to objects and datatypes.
```python
# Function
def some_random_stuff():
    pass
some_random_stuff()

# Method
'hello'.capitalize()
```

## Docstrings
These can be added to provide hints for this function in your code editor.
```python
def test(a):
    '''
    Info: this function tests and prints param a
    '''
    print(a)

help(test)
# test(a)
#   Info: this function tests and prints param a
# END
print(test.__doc__)
#   Info: this function tests and prints param a
```

## Clean Code
Consider the following function:
```python
def is_even(num):
    if num % 2 == 0:
        return True
    elif num % 2 != 0:
        return False
print(is_even(51)) # False
```
After cleaning:
```python
def is_even(num):
    return num % 2 == 0:
print(is_even(50)) # True
```

## *args and **kwargs
By adding `*` in front of the params definition, we allow mutiple arguments to be used when calling the function:
```python
def super_func(*args):
    print(args) # (1,2,3,4,5)
    return sum(args)

print(super_func(1,2,3,4,5)) # 15
```
Adding `**` is similar but these are for keyword args:
```python
def super_func(*args, **kwargs):
    total = 0
    for items in kwargs.values():
        total += items
    return sum(args) + total

print(super_func(1,2,3,4,5, num1=5, num2-10)) # 30
```
:::note
Must be in order: params, *args, default params, **kwargs
:::

## Walrus Operator
In below example, we are calling `len(a)` twice:
```python
a = 'helloooooooooo'

if (len(a) > 10):
    print(f'too long {len(a)} elements') # too long 14 elements
```
With walrus, we can avoid repeating:
```python
a = 'helloooooooooo'

if ((n := len(a)) > 10):
    print(f'too long {n} elements') # too long 14 elements

while ((n := len(a)) > 1):
    print(n)
    a = a[:-1]
print(a)
# 14
# 13
# 12
# 11
# 10
# 9
# 8
# 7
# 6
# 5
# 4
# 3
# 2
# h
```