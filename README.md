# Amman Academy Python Cheat Sheet
- [Amman Academy Python Cheat Sheet](#amman-academy-python-cheat-sheet)
  - [The print() statement](#the-print-statement)
  - [Variable assignemnt](#variable-assignemnt)
  - [Commenting](#commenting)
  - [Getting user input using input()](#getting-user-input-using-input)
  - [Data types](#data-types)
    - [Number Operators (Ints and Floats)](#number-operators-ints-and-floats)
    - [Relational Operators](#relational-operators)
    - [Boolean Operators](#boolean-operators)
    - [String Operators](#string-operators)
  - [Type conversion](#type-conversion)

print
input
comments
variables
datatypes
operators


## The print() statement
We start with the humble rite-of-passage to any programming language, 'Hello world!'

```python
print('Hello world!')
```

Note that there is no space between the *print* and the parentheses. While the code will work with a space, it is against convention to do so.

## Variable assignemnt
You can create variables that store data for you, and reference the variable name whenever you want to retrieve the data. We go over different types of data that Python supports below.

Variable names must start with a letter or underscore, contain only letters, numbers, or underscores, and cannot be special keywords otherwise used in Python.

You can assign a variable by using the single equals sign  `=`. The left side of the equals sign has the variable name, and the right side has the value to assign to the variable.

```python
name = 'Johnny'
pi = 3.14
answer = 42
```

And you can print the value of a variable by referencing the variable name:

```python
print('Johnny') # prints 'Johnny'
print(name) # also prints 'Johnny'
```

Note that if you later assign a value to the same variable name, it will overwrite the previous value.

```python
print(answer) # prints 42
answer = 100 
print(answer) # prints 100
```

## Commenting
You have already seen commenting above! There are two ways to comment:
- Inline comments are denoted by `#` and all code between the `#` and the end of the line will not be run
- Block comments start and end with `"""` (triple quotation marks) and all code between the two will not be run

```python
print('This is not commented') # but this is
# print('I don't want to see this message')

"""
Nothing in this block will run.
print("I don't want to see this either.")

"""

```

## Getting user input using input()
Now, we want to print something based on what the user enters. You can greet the user by asking for their name and saying 'Hello {name}!' where {name} is replaced with their actual name. 

```python
# set a variable 'name' equal to the user input to the question 'What's your name?'
name = input("What's your name? ")
# greet the user with a print statement, concatenating 'Hello ' before their name
print('Hello ' + name)
```

Note that there is a space in the string `"Hello "` has a space before the closing quote. We go over this in the section about concatenation.

Equivalently, your print statement can be `print('Hello', name)`. Having two parameters (each parameter is in the parentheses of the print statement separated by the comma) means that Python will print the two strings with a space in between. Note there is no extra space in `"Hello"` in this case.

## Data types
There are many built-in data types in Python, you can see them all [in the documentation](https://docs.python.org/3.7/library/stdtypes.html). 

Let's focus on four main ones:
- Strings (`str`): text, denoted in variable assignemnts by quotation marks. Strings are immutable
- Integers (`int`): whole numbers. Integers are mutable.
- Floats (`float`): decimal numbers. Decimals are mutable.
- Booleans (`bool`): True or False. Booleans are not mutable.

### Number Operators (Ints and Floats)
You can make math calculations using Python just like a calculator. Both inputs must be a number, otherwise a type error will result.

```python
var1 = 10
var2 = 2
# Addition
print(var1 + var2) # prints 12
# Subtraction
print(var1 - var2) # prints 8
# Multiplication
print(var1 * var2) # prints 20
# Division
print(var1 / var2) # prints 5
# Exponentiation
print(var1 ** var2) # prints 100
# Modulus (remainder of a division)
print(var1 % var2) # prints 0
```

### Relational Operators
These operators can be applied to two variables and produce a boolean.

```python
x = 2
y = 3

# Equals
print(x == x) # prints True
print(x == y) # prints False

# Not Equal
print(x != x) # prints False
print(x != y) # prints True

# Greater than
print(x > y) # prints False

# Less than
print(x < y) # prints True

# Greater than or equal to
print(x >= y) # prints False

# Less than or equal to
print (x <= y) # prints True
```

### Boolean Operators
There are also logical operators in Python: *and*, *or*, & *not*.
- and: `True` ONLY if both sides are `True`
- or: `True` if either side is `True`
- not: inverts `True` and `False`

```python
print(True and True) # prints True
print(True and False) # prints False

print(True or False) # prints True
print(False or False) # prints False

print(not True) # prints False
print(not False) # prints True
```

### String Operators
You can also operate on strings through concatenation, repetition, indexing, and slicing.

- Concatenation is denoted by a `+` and will connect two strings together
- Repetition is denoted by a `*` and will repeat a string a certain number of times specified by an integer
- Indexing into a string uses brackets `[index]` and will return a specific letter from the string, where the first letter is index zero
- Slicing into a string also uses brackets `[start:stop]` with a colon and will return a specific subset of the string, where the first letter is also index zero. Note that the first number is the start index inclusive and the second number is the stop index exclusive. 

```python
# concatenation
print('hello' + 'world') # prints 'helloworld'
print('hello ' + 'world') # prints 'hello world'

# repetition
print('ha'*3) # prints 'hahaha'

# indexing
print('super'[0]) # prints 's'
x = 'hello'
print(x[1]) # prints 'e'

# slicing
print('super'[0:3]) # prints 'sup'
print(x[0:5]) # prints 'hello'
```

Some notes about slicing: If you omit a start or stop index, Python will assume that you want to go to the end of the string. In addition, if you use negative indices, it will count backward from the end of the string.
```python
x = 'superhero'
print(x[1:]) # prints 'uperhero'
print(x[:2]) # prints 'su'
print(x[:-1]) # prints 'superher'
```

## Type conversion
You can switch between different types by casting. This is useful if you are trying to concatenate a string and a number, or if you want to add two numbers together that are currently strings.

You can convert data to:
- floats with `float()`
- integers with `int()`
- strings with `str()`

You can also get the type with the `type()` function.

```python
print('kit' + 3) # returns Type Error
print('kit' + str(3)) # returns 'kit3'
print(float(3)) # returns 3.0

x = '2'
y = '3'
print(x + y) # returns '23'
print(int(x) + int(y)) # returns 5

z = 9
print(type(x) == int) # returns True
```