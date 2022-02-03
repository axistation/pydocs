---
sidebar_position: 6
---

# Scope

What variables do I have access to?  When we create a function, we create a new scope.

```python
if True:
    x = 10
def some_func():
    total = 100
print(x) # 10
print(total) # NameError
```

## Scope Rules
Consider the following:
```python
a = 1

def confusion():
    a = 5
    return a

print(a) # 1
print(confusion()) # 5
```
And if we change order of `print`:
```python
a = 1

def confusion():
    a = 5
    return a

print(confusion()) # 5
print(a) # 1
```
When checking for which variables to use, the rule is as follows:
1. Start with local
2. Parent local
3. Global
4. Is it a built-in python function?
```tip
When creating functions, params are considered local variables.
```
## global Keyword
Sometimes we want to use global variables in our function:
```python
total = 0

def count():
    global total
    total += 1
    return total

print(count()) # 1
print(count()) # 2
print(count()) # 3
```
But actually is this not a good way to do things, with global everywere.  Use dependency injection instead:
```python
total = 0

def count(total):
    total += 1
    return total

print(count(count(count(total)))) # 3
```

## nonlocal Keyword
This refers specifically to parent local.  Consider the following example:
```python
def outer():
    x = 'local'
    def inner():
        nonlocal x
        x = 'nonlocal'
        print('inner', x)
    
    inner()
    print('outer', x)

outer()
# inner: nonlocal
# outer: nonlocal
```
And if we remove `nonlocal`:
```python
def outer():
    x = 'local'
    def inner():
        # nonlocal x
        x = 'nonlocal'
        print('inner', x)
    
    inner()
    print('outer', x)

outer()
# inner: nonlocal
# outer: local
```
By not using `nonlocal`, we are no longer reassigning `x` inside `inner()`.
:::tip
Try to avoid using `global` and `nonlocal` to make your code easier to read.  But they are useful in some situations.
:::

## Why not have everything as global?
Machines do not have infinite memory, and with scope, we can create new variables only when necessary.  Also as soon as we finish running a function, its variables automatically gets destroyed in memory, hence saving resources.

:::tip
Scope help us write code and programs that do not hog our machine's memory.
:::