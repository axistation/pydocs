---
sidebar_position: 3
---

# Conditionals

## if statements
```python
is_old = True
is_licensed = True

if is_old:
  print('you are old enough to drive!')
print('checkcheck')
# you are old enough to drive!
# checkcheck

is_old = False

if is_old:
  print('you are old enough to drive!')
print('checkcheck')
# checkcheck

if is_old:
  print('you are old enough to drive!')
elif is_licensed:
  print('you can drive now!')
else:
  print('you are not of age!')
print('okok')
# you can drive now!
# okok

is_old = True

if is_old and is_licensed:
  print('you are old enough to drive, and you have a license!')
else:
  print('you are not of age!')
print('okok')
# you are old enough to drive, and you have a license!
# okok

```

:::tip
Python does not see indentations as just styling, but also to define code block.  
Usually indents are created using a tab or 4 spaces.
:::

## Truthy vs Falsey
All values are considered truthy except for the following, which are falsey:
```python
None
False
0
0.0
0j
Decimal(0)
Fraction(0, 1)
[]
{}
()
''
b''
set()
range(0)
obj.__bool__() returns False
obj.__len__() returns 0
```
This is useful to check if there is a value and then do something:
```python
username = 'Johnny'
password = '123'

if username and password:
  # do something
else:
  # do something else
```

## Ternary Operator
Also know as conditional expression.
```python
is_friend = True
can_message = 'message allowerd' if is_friend else'not allowed to message'
```

## Short Circuiting
In the below example, `is_user` is never evaluated because `is_friend` is already evaluated to `True`.
```python
is_friend = True
is_user = True
if is_friend or is_user:
  print('best friends forever')
# best friends forever

is_friend = False
is_user = True
if is_friend and is_user:
  print('best friends forever')
# best friends forever
# as soon as it sees False, then the second expression is_user does not matter
```

## Logical Operators
```python
# < > == >= <= !=
# and or not
```
:::tip
`not` can also be used as a function.
:::

## is vs ==
```python
# for ==, the test returns True of the two objects have the same value
print(True == 1) # True
print('1' == 1) # False
print([] == 1) # False
print(10 == 10.0) # True
print([1, 2, 3] == [1, 2, 3]) # True

# for is, the test returns True if two objects are the same object
print(True is True) # True
print('1' is '1') # True
print([] is []) # False
print(10 is 10) # True
print([1, 2, 3] is [1, 2, 3]) # False
```
:::tip
Every time you create a list, it is created in a new memory space.
:::