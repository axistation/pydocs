---
sidebar_position: 4
---

# Loops

Run lines of code over and over.

## For Loops
Allows use to iterate over a iterable, or collection of items.
```python
for item in [1, 2, 3, 4, 5]:
  print(item)
# 1
# 2
# 3
# 4
# 5
print(item) # 5
for item in (1, 2, 3):
  for x in ['a', 'b', 'c']:
    print(item, x)
# 1, a
# 1, b
# 1, c
# 2, a
# 2, b
# 2, c
# 3, a
# 3, b
# 3, c
```

## Iterables
Object or collection that can be iterated over.  Ony by one check each item in the collection.
- list
- dict
- tuple
- set
- string

Dictionaries are also iterables.

```python
user = {
  'name': 'Golem',
  'age': 5006,
  'can_swim': False
}
for item in user.items():
  print(item)
# ('name': 'Golem')
# ('age': 5006)
# ('can_swim': False)
for item in user.values():
  print(item)
# Golem
# 5006
# False
for item in user.keys():
  print(item)
# name
# age
# can_swim
for key, value in user.items():
  print(key, value)
# name Golem
# age 5006
# can_swim False
```

## Looping with range()
```python
for number in range(0, 5):
  print(number)
# 0
# 1
# 2
# 3
# 4
for number in range(0, 10, 2):
  print(number)
# 0
# 2
# 4
# 6
# 8
for number in range(10, 0, -2):
  print(number)
# 10
# 8
# 6
# 4
# 2
for _ in range(2):
  print(list(range(5)))
# [0, 1, 2, 3, 4]
# [0, 1, 2, 3, 4]
```

## Looping with enumerate()
We get an index counter for free with enumerate.
```python
for index, char in enumerate('Hello'):
  print(index, char)
# 0 H
# 1 e
# 2 l
# 3 l
# 4 o

for index, char in enumerate(list(range(5))):
  if char == 2:
    print(f'index of 2 is: {index}')
# index of 2 is: 2
```

## While Loops
Loop until a condition becomes `False`.

```python
i = 0
while i < 5:
  print(i)
  i += 1 # prevent infinite loop
else:
  print('done with all the work')
# 0
# 1
# 2
# 3
# 4
# done with all the work
```
```python
i = 0
while i < 5:
  print(i)
  i += 1 # prevent infinite loop
  break # with break, the else block would not run
else:
  print('done with all the work')
# 0
# 1
# 2
# 3
# 4
```
:::tip
Beware of infinte loops.
:::

## while loops vs for loops
- for loops simpler
- for loops good for looping fixed number of items
- while loops is more flexible about number of items
- need to remember to halt the while loop
- while loops are useful when prompting for input
```python
my_list = [1, 2, 3]

for item in my_list:
  print(item)
# 1
# 2
# 3

i = 0
while i < len(my_list):
  print(my_list[i])
  i += 1
# 1
# 2
# 3

while True:
  response = input('say something: ')
  if (response == 'bye'):
    break
# say something: hi
# say something: bye
```

## Break, continue, pass
These work for both for and while loops.
### break
```python
my_list = [1, 2, 3]

for item in my_list:
  print(item)
  break
# 1

i = 0
while i < len(my_list):
  print(my_list[i])
  i += 1
  break
# 1
```

### continue
```python
my_list = [1, 2, 3]

for item in my_list:
  continue
  print(item)
# nothing prints as continue tell loop to interate next loop before the print statement

i = 0
while i < len(my_list):
  i += 1
  continue
  print(my_list[i])
# nothing prints as continue tell loop to interate next loop before the print statement
```

### pass
Used as a placeholder when still not sure what code to execute in that block block.  Without `pass`, the for loop will give error.
```python
my_list = [1, 2, 3]

for item in my_list:
  # thinking about it
  pass
```