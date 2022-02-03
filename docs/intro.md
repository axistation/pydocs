---
slug: /
sidebar_position: 1
---

# Intro

Before diving into Python, let's take a look at what a programming language is.

## What is a programming language?

Programming is simply a way for us to give instructions to computers to perform actions on data.  Without programs, computer wouldn't do anything.

We write source code that reads more like English, which gets translated to binary (bytecode) that computer understands.

The translation is done using an interpreter or compiler:
1. Interpreter - Excecute code line-by-line
2. Compiler - Read code all at once and then translate

![What is a programming lanaguage?](/img/tutorial/intro-01.png)

:::note
Python usually uses an interpreter.
:::

### Python interpreter
When most people talk about Python, they're most likely talking about the implementation, the specification.  You see, there are many Python interpreters and compiler.

For Example:
- [Python.org](https://www.python.org/) lets you download the C Python translator.
- [Jython Project](https://www.jython.org) lets you download the Java Python translator.
- [pypy](https://pypy.org) lets you download Python translator written in Python itself.

Once Python code is translated to bytecode, which gets run in the CPython VM (in the case of CPython), then binary code gets run on the machine.

## Run Python code

- Terminal
- Code Editors
  - Sublime Text
  - VSCode
- IDEs
  - PyCharm
  - Spyder
- Notebooks
  - Jupyter
- Online IDE
  - [repl.it](https://repl.it)
  - [glot.io](https://glot.io)

## First Python program

Create a new python file `main.py`:
```python title='main.py'
print('Hello World!")
```
Running the above code prints the following to console:
```bash
Hello World!
```

### User input

Prompt user for information:
```python title='main.py'
name = input('What is your name?')
print('Hello ' + name)
```
After entering the info:
```bash
What is your name?Andy
Hello Andy
```

## Python 2 vs Python 3

A language is always evolving, and in 2008, Guido decided to create Python 3, which introduced many breaking changes for the better.

- [The Story of Python](https://youtube.com/watch?v=J0Aq44Pze-w)
- [Python 2 vs Python 3](https://sebastianraschka.com/Articles/2014_python_2_3_key_diff.html)
- [Python 2 vs Python 3](https://www.geeksforgeeks.org/important-differences-between-python-2-x-and-python-3-x-with-examples/)

:::note
Python 2 is no longer maintained.  Python 3 is the way to go!
:::

## Why are there so many languages?

In your career, you don't need to know all languages.  Specialize in popular ones.  Different languages are good at different things.  There is no utlimate langauge and everything has a trade-off.  Learn to decide when to use what.

- Python is slower than Java and C++
- Python is easy to learn and read
- Python uses less lines of code and boosts productivity

## Learning Python

1. Terms
2. Data Types
3. Actions
4. Best Practices

![Learning Python](/img/tutorial/intro-02.png)