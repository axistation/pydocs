---
sidebar_position: 2
---

# Data Structures

## list
```python
li = [1, 2, 3, 4, 5]
li2 = ['a', 'b', 'c']
li3 = [1, 'b', True]

amazon_cart = ['notebooks', 'sunglasses']
print(amazon_cart[1]) # sunglasses 
print(amazon_cart[2]) # IndexError 
```

### list slicing
```python
amazon_cart = [
    'notebooks',
    'sunglasses',
    'toys',
    'grapes'
]
print(amazon_cart[0:2]) # ['notebooks', 'sunglasses']
print(amazon_cart[0::2]) # ['notebooks', 'toys']
```

:::note
Unlike strings, lists are mutable.  
But slicing still creates new lists.
:::

```python
amazon_cart[0] = 'laptop'
print(amazon_cart) # ['laptop', 'sunglasses', 'toys', 'grapes']
```

What happens if?
```python
new_cart = amazon_cart
new_cart[0] = 'gum'
print(new_cart) # ['gum', 'sunglasses', 'toys', 'grapes']
print(amazon_cart) # ['gum', 'sunglasses', 'toys', 'grapes']
```
You can see that `new_cart` has been assigned `amazon_cart`, changing it will also change the original values in memory.  To make a copy use slicing instead:
```python
new_cart = amazon_cart[:]
```

### matrix
This is where lists are nested within a list.
```python
matrix = [
    [1, 2, 3],
    [2, 4, 5],
    [7, 8, 9]
]
print(matrix[0][1]) # 2
```
:::tip
    Matrices can be 2D or 3D, and are commonly used in machine learning or things like image recognition.
:::

### list methods
```python
basket = [1, 2, 3, 4, 5]

new_list = basket.append(100)
print(basket) # [1, 2, 3, 4, 5, 100]
print(new_list) # None

basket.insert(4, 200)
print(basket) # [1, 2, 3, 4, 200, 5, 100]

basket.extend([300, 301])
print(basket) # [1, 2, 3, 4, 200, 5, 100, 300, 301]

basket.pop()
print(basket) # [1, 2, 3, 4, 200, 5, 100, 300]

removed_item = basket.pop(4)
print(basket) # [1, 2, 3, 4, 5, 100, 300]
print(removed_item) # 200

basket.pop(300)
print(basket) # [1, 2, 3, 4, 5, 100]

basket.clear()
print(basket) # []
```
:::note
Some methods such as `.append()`, `.insert()`, `.extend()`, `.remove()`, and `.clear()` changes a list in place, and does not return a value.  Other methods like `.pop()` do return some value.
:::

### more list methods
```python
basket = ['a', 'b', 'c', 'd', 'e']

print(basket.index('d')) # 3
print(basket.index('d', 0, 2)) # ValueError
print('d' in basket) # True
print('x' in basket) # False
print(basket.count('d')) # 1
```
:::tip
The keyword `in` also works for strings.
:::

Here are some more useful list methods:

```python
basket = ['a', 'x', 'b', 'c', 'd', 'e', 'd']

basket.sort()
print(basket) # ['a', 'b', 'c', 'd', 'd', 'e', 'x']

new_basket = basket.copy()
print(new_basket) # ['a', 'b', 'c', 'd', 'd', 'e', 'x']

basket.reverse() # ['x', 'e', 'd', 'd', 'c', 'b', 'a']
```
:::note
In contrast to the `.sort()` method that changes the list in place, Python has a function `sorted()` that returns a new sorted list.

The `.reverse()` methodd only reverse the list, but does not sort it.
:::

### Common List Patterns
```python
basket = ['a', 'x', 'b', 'c', 'd', 'e', 'd']

# Find length of list
print(len(basket)) # 7

# Reverse list
print(basket[::-1]) # ['d', 'e', 'd', 'c', 'b', 'x', 'a']

# Using range to generate list
print(range(1, 6)) # [1, 2, 3, 4, 5]
print(range(6)) # [0, 1, 2, 3, 4, 5]

# Using .join()
new_sentence = '!'.join(['hi', 'my', 'name', 'is', 'JOJO'])
print(new_sentence) # hi!my!name!is!JOJO
```

### List Unpacking
```python
a, b, c, *other, d = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(a) # 1
print(b) # 2
print(c) # 3
print(other) # [4, 5, 6, 7, 8]
print(d) # 9
```

## dict
A dictionary consists of unordered key-value pairs making up the items.
```python
dictionary = {
    'a': [1, 2, 3],
    'b': 'hello',
    'c': True
}
print(dictionary['a']) # [1, 2, 3]
print(dictionary['a'][1]) # 2

my_list = [
    {
        'a': [1, 2, 3],
        'b': 'hello',
        'c': True
    },
    {
        'a': [4, 5, 6],
        'b': 'hello',
        'c': True
    },
]
print(my_list[1][a][2]) # 6
```

:::note
Each item in a dictionary is stored in different memory locations and not in order that they were created.
:::

### Dictionary Keys
```python
dictionary = {
    123: [1, 2, 3],
    True: 'hello',
    [100]: True
}
print(dictionary[123]) # [1, 2, 3]
print(dictionary[True]) # hello
print(dictionary[[100]]) # TypeError
```
:::note
Dictionary keys must be hashable, meaning that they must be immutable.  In the above example, the key `[100]` is a list that is unhasahable (it can change over its lifetime).
:::

Dictionary keys must also be unique.

```python
dictionary = {
    '123': [1, 2, 3],
    '123': 'hello'
}
print(dictionary['123']) # hello (previous value was overwritten)
```

### Dictionary Methods
```python
user = {
    'basket': [1, 2, 3],
    'greet': 'hello'
}

print(user['age']) # KeyError

# .get method
print(user.get('age')) # None
print(user.get('age', 55)) # 55

# create dictionary using dict() function
user2 = dict(name = 'JohnJohn')
print(user2) # {'name': 'JohnJohn'}

# look for item in dictionary
user3 = {
    'basket': [1, 2, 3],
    'greet': 'hello',
    'age': 20
}
print('basket' in user3) # True
print('size' in user3) # False
print('age' in user3.keys()) # True
print('hello' in user3.values()) # True
print(user3.items()) # dict_items([('basket', [1, 2, 3]), ('greet', 'hello'), ('age', 20)])
```
:::tip
The `.items()` method returns a `dict_item` object containing a list of items in the form of tuples.
:::

### More dictionary methods

```python
# Clear all items
user4 = {
    'basket': [1, 2, 3],
    'greet': 'hello',
    'age': 20
}
user4.clear()
print(user4) # {}

# copy dictionary
user5 = {
    'basket': [1, 2, 3],
    'greet': 'hello',
    'age': 20
}
user6 = user4.copy()
print(user5) # {'basket': [1, 2, 3], 'greet': 'hello', 'age': 20}
print(user6) # {'basket': [1, 2, 3], 'greet': 'hello', 'age': 20}

# Remove item
user7 = {
    'basket': [1, 2, 3],
    'greet': 'hello',
    'age': 20
}
print(user7.pop('age')) # 20
print(user7) # {'basket': [1, 2, 3], 'greet': 'hello'}

# Remove last item key-value pair
user8 = {
    'basket': [1, 2, 3],
    'greet': 'hello',
    'age': 20
}
print(user8.popitem()) # ('age': 20)
print(user8) # {'basket': [1, 2, 3], 'greet': 'hello'}

# Update items
user9 = {
    'basket': [1, 2, 3],
    'greet': 'hello',
    'age': 20
}

print(user9.update({'age': 55}))
print(user9) # {'basket': [1, 2, 3], 'greet': 'hello', 'age': 55}
print(user9.update({'sex': 'M'}))
print(user9) # {'basket': [1, 2, 3], 'greet': 'hello', 'age': 55, 'sex': 'M'}
```
:::tip
The method `popitem()` is useful for destructively iterate over a dictionary.
:::

## tuple

They are kind of like ummutable lists.

```python
my_tuple = (1, 2, 3, 4, 5)
my_tuple[1] = 'z' # TypeError (tuples are immmutable)

print(my_tuple[1]) # 2
print(5 in my_tuple) # True
```
:::note
Tuples are more predictable but less flexible than lists.  They can also be used as keys in dictionaries.
:::

### Slicing tuples
```python
my_tuple = (1, 2, 3, 4, 5)

print(my_tuple[1:2]) # (2,)
print(my_tuple[1:4]) # (2, 3, 4)

x, y, z, *other = (1, 2, 3, 4, 5)
print(x) # 1
print(y) # 2
print(z) # 3
print(other) # [4, 5]
```

### Tuple methods
```python
my_tuple = (1, 2, 3, 4, 5, 5)

print(my_tuple.count(5)) # 2
print(my_tuple.index(5)) # 4 (first occurence)

print(len(my_tuple)) # 6
```
## set
These are simply unordered collection of unique objects.

```python
my_set = {1, 2, 3, 4, 5, 5}

print(my_set) # {1, 2, 3, 4, 5}

my_set.add(100)
my_set.add(2)

print(my_set) # {1, 2, 3, 4, 5, 100}
print(my_set[0]) # TypeError (sets have no indexing or order)
print(1 in my_set) # True
print(len(my_set)) # 6

new_set = my_set.copy()
my_set.clear()

print(new_set) # {1, 2, 3, 4, 5, 100}
print(my_set) # set()
```

### Set methods

```python
my_set = {1, 2, 3, 4, 5}
your_set = {4, 5, 6, 7, 8, 9, 10}

# .difference()
print(my_set.difference(your_set)) # {1, 2, 3}

# .discard()
print(my_set.discard(5)) # None
print(my_set) # {1, 2, 3, 4}

# .difference_update()
print(my_set.difference_update(your_set)) # None
print(my_set) # {1, 2, 3}
```

### More set methods
```python
my_set = {1, 2, 3, 4, 5}
your_set = {4, 5, 6, 7, 8, 9, 10}

# .intersection()
print(my_set.intersection(your_set)) # {4, 5}
print(my_set & your_set) # {4, 5}

# .isdisjoint(your_set)
print(myset.isdisjoint(your_set)) # False (they have items in common)

# .union()
print(my_set.union(your_set)) # {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
print(my_set | your_set) # {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}

my_set = {4, 5}

# .issubset()
print(my_set.issubset(your_set)) # True

# .issuperset()
print(my_set.issuperset(your_set)) # False
print(your_set.issuperset(my_set)) # True
```