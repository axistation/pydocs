---
sidebar_position: 1
---

# Data Types

This is what kind of data can a program use.  Think of it as values.  In programming, we have these data types to store information.

## Numbers

### int
```python
print(2 + 4) # 6
print(2 - 4) # -2
print(2 * 4) # 8
print(type(2 + 4)) # <class 'int'>
print(type(0)) # <class 'int'>
```
### float
```python
print(2 / 4) # 0.5
print(type(2 / 4)) # <class 'float'>
print(type(20 + 1.1) # <class 'float'>
print(9.9 + 1.1) # 11.0
```
:::note
Float take up more space in memory than int.
:::
### more operators
```python
print(2 ** 3) # 8 (squaring)
print(5 // 4) # 1 (round down)
print(5 % 2) # 1 (modulo)
```

### math functions
```python
print(round(3.1)) # 3
print(round(3.9)) # 4
print(abs(-20)) # 20
```

### operator precedence
```python
# ()
# **
# * /
# + -
```

### binary
```python
print(bin(5)) # 0b101
print(int('0b101', 2)) # 5
```

:::note
There is also a Complex number type in Python.
:::

## Variables
Store information that we can use in our programs.  We are assigning (binding) the value `190` to variable name `iq`.  Then we retrieve the value in memory by referencing to the variable name.
```python
iq = 190
print(iq) # 190
a,b,c = 1,2,3

print(1) # a
print(2) # b
print(3) # c
```
:::note
Variables can be reassigned.
:::
### naming variables
- snake_case
- Start with lowercase or underscore
- Letters, numbers, underscores
- Case sensitive
- Don't overwrite [keywords](https://www.w3schools.com/python/python_ref_keywords.asp)

### constants
Although not restricted, a good convention is to capatalize constants:
```python
PI = 3.14
```
Aside from the above rules, try make variable names as descriptive as possible, so that everyone can easy read and understand your code.

:::tip
Private _variables start with a single underscore.  
Dunder \_\_variables\_\_ start with double underscores.
:::

## Expressions vs Statements
In the below example, `100` and `iq / 5` are expressions, they are a piece of code that produces a value.  Statements are an entire line of code that does something:
```python
iq = 100 # Statement
user_age = iq / 5 # Statement
```

## Augmented assignment operator
```python
some_value = 5
some_value = some_value + 2
some_value += 2
print(some_value) # 9
some_value *= 2
print(some_value) # 18
```

## Strings

### str
```python
print('hi hello there 24!') # hi hello there 24!
print("hi hello there 24!") # hi hello there 24!
print(type('hi')) # <class 'str'>

username = 'supercode'
password = 'supersecret'

long_string = '''
WOW
0 0
___
'''
print(long_string)
# WOW
# 0 0
# ___

print('Hello' + ' ' + 'Andy') # Hello Andy
```

### type conversion
```python
print('Hello' + 5) # TypeError
print('Hello ' + str(5)) # Hello 5
```

### escape sequences
```python
print('It's "kind of" sunny') # error
print('It\'s \"kind of\" sunny') # It's "kind of" sunny

print('New Year \\ Christmas') # New Year \ Christmas
print('\t indented') #  indented
print('Hello \n Andy')
# Hello
# Andy
```

### formatted strings
```python
name = 'Johnny'
age = 55
print(f'hi {name}.  You are {age} years old') # hi Johnny.  You are 55 years old

# Python 2
print('hi {name}.  You are {age} years old'.format(name='sally', age=100)) # hi sally.  You are 100 years old
```

### string indexes
Access different parts of a string.
```python
selfish = '01234567'
#          01234567
print(selfish[0]) # 0
print(selfish[7]) # 7

# string slicing
print(selfish[0:5]) # 01234
print(selfish[0:8:2]) # 0246
print(selfish[1:]) # 1234567
print(selfish[:5]) # 01234
print(selfish[-1]) # 7
print(selfish[::-1]) # 7654321
```

### immutability
Strings are immmutable, and cannot be changed in parts.  However, it can be completely reassigned.
```python
selfish = '01234567'
selfish = 100
print(selfish) # 100

# strings are immutable
selfish[0] = '8' # error

# this works because we are create a completely new string
selfish = selfish + '8' # 012345678
```

### built-in functions and methods
Functions have syntax `function()` whereas method has syntax 'obj.method()'.  Methods are owned by something, such as methods only for string objects.
```python
# functions
greet = 'hellloooo'
print(greet[0:len(greet)]) # hellloooo

# methods
quote = 'to be or not to be'
print(quote.upper()) # TO BE OR NOT TO BE
print(quote.capitalize()) # To Be Or Not To Be
print(quote.find('be')) # 3
print(quote.replace('be', 'me')) # to me or not to me

# original string is never modified
# previous examples all create new strings
print(quote) # to be or not to be
```

## Booleans

### bool
```python
is_cool = True
is_cool = False
print(bool(1)) # True
print(bool(10)) # True
print(bool(0)) # False
print(bool('True')) # True
```

## None
This is a type that represents the absence of value.  It's just nothing.
```python
weapons = None
print(weapons) # None
```
:::Note
We saw that some list methods do actually return `None`.
:::