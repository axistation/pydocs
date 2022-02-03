---
sidebar_position: 4
---

# Exercises

## Operator Precedence
Guess the output:
```python
print((5 + 4) * 10 / 2)
print(((5 + 4) * 10) /2)
print((5 + 4) * (10 / 2))
print(5 + (4 * 10) / 2)
print(5 + 4 * 10 // 2)
```
<details>
    <summary>Solution</summary>

```python
# 45.0
# 45.0
# 45.0
# 25.0
# 25
```
:::note
Operator `/` returns float and `//` rounds to int. 
:::
</details>

## Type conversion
Calculate the age after getting user input:

```python
birth_year = input('what year were you born?')
```

<details>
    <summary>Solution</summary>

```python
birth_year = input('what year were you born?')
age = 2022 - int(birth_year)
print(f'you age is: {age}')
```
:::note
The function `input()` returns a string.
:::
</details>

## Password checker
Prompt user for username and password, check the password length and convert it to *, and then print it out.
```python
username = input('what is your username?')
password = input('what is your password?')
```
<details>
  <summary>Solution</summary>

```python
username = input('what is your username?')
password = input('what is your password?')

password_length = len(password)
hidden_password = '*' * password_length

print(f'{username}, you password, {hidden_password}, is {password_length} letters long')
```
</details>

## Logical Operators
Check for the follwing:
- Magician and expert "you are a master magician"
- Magician but not expert "at least you're getting there"
- Not magician "you need magic powers"

<details>
  <summary>Solution</summary>

```python
is_magician = False
is_expert = True

if is_magician and is_expert:
  print('you are a master magician')
elif is_magician and not is_expert:
  print('at least you\'re getting there')
elif not is_magician:
  print('you need magic powers')
```
</details>

## Tricky Counter

Calculate the total of the items in a list:

```python
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

<details>
  <summary>Solution</summary>

```python
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

counter = 0
for item in my_list:
  counter = counter + item
print(counter)
```
</details>

## Our First GUI
Iterate ofver `picture`.  If `0`, then print `''`, if `1`, then print `*`.

```python
picture = [
  [0,0,0,1,0,0,0],
  [0,0,1,1,1,0,0],
  [0,1,1,1,1,1,0],
  [1,1,1,1,1,1,1],
  [0,0,0,1,0,0,0],
  [0,0,0,1,0,0,0],
]
```

<details>
  <summary>Solutions</summary>

```python
for row in picture:
  for pixel in row:
    if (pixel == 1):
      print('*', end='')
    else:
      print(' ', end='')
  print('')
```
cleaned up
```python
fill = '*'
empty = ' '
for row in picture:
  for pixel in row:
    if (pixel):
      print(fill, end='')
    else:
      print(empty, end='')
  print('')
```
</details>

## Find Duplicates
Check for duplicates in list
```python
some_list = ['a', 'b', 'c', 'b', 'd', 'm', 'n', 'n']
```

<details>
  <summary>Solution</summary>

```python
duplicates = []
for value in some_list:
  if some_list.count(value) > 1:
    if value not in duplicates:
      duplicates.append(value)

print(duplicates)
```
</details>

## Tesla
1. Wrap the below code in a function called `checkDriverAge()`. Whenever you call this function, you will get prompted for age. 

2. Instead of using the `input()`. Now, make the `checkDriverAge()` function accept an argument of age, so that if you enter `checkDriverAge(92)`
it returns "Powering On. Enjoy the ride!".  Also make it so that the default age is set to 0 if no argument is given.
```python
age = input("What is your age?: ")

if int(age) < 18:
	print("Sorry, you are too young to drive this car. Powering off")
elif int(age) > 18:
	print("Powering On. Enjoy the ride!");
elif int(age) == 18:
	print("Congratulations on your first year of driving. Enjoy the ride!")
```

<details>
  <summary>Solution</summary>

```python
def checkDriverAge():
  age = input("What is your age?: ")
  if int(age) < 18:
    print("Sorry, you are too young to drive this car. Powering off")
  elif int(age) > 18:
    print("Powering On. Enjoy the ride!");
  elif int(age) == 18:
    print("Congratulations on your first year of driving. Enjoy the ride!")

checkDriverAge()

def checkDriverAge(age=0):
  if int(age) < 18:
    print("Sorry, you are too young to drive this car. Powering off")
  elif int(age) > 18:
    print("Powering On. Enjoy the ride!");
  elif int(age) == 18:
    print("Congratulations on your first year of driving. Enjoy the ride!")

checkDriverAge(92) # Power On.  Enjoy the ride!
checkDriverAge() # Sorry, you are too young to drive this car. Powering off
```
</details>

## Functions
Create function that finds the highest even number in a list of numbers.
<details>
  <summary>Solution</summary>

```python
def highest_even(li):
  evens = []
  for item in li:
    if item & 2 == 0
      evens.append(item)
  return max(evens)

print(highest_even(2,10,2,3,4,8,11)) # 10
```
</details>
