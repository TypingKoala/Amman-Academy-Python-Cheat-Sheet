# Amman Academy Python Cheat Sheet
- [Amman Academy Python Cheat Sheet](#amman-academy-python-cheat-sheet)
  - [The print() statement](#the-print-statement)
  - [Variable assignment](#variable-assignment)
  - [Commenting](#commenting)
  - [Getting user input using input()](#getting-user-input-using-input)
  - [Data types](#data-types)
    - [Number Operators (Ints and Floats)](#number-operators-ints-and-floats)
    - [Relational Operators](#relational-operators)
    - [Boolean Operators](#boolean-operators)
    - [String Operators](#string-operators)
  - [Type conversion](#type-conversion)
  - [Conditionals (If/Else)](#conditionals-ifelse)
  - [For Loops](#for-loops)
  - [The mighty range() function](#the-mighty-range-function)
  - [While Loops](#while-loops)
  - [Functions and Writing Modular Code](#functions-and-writing-modular-code)

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

## Variable assignment
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
These operators can be applied to two variables and produce a boolean. These are helpful for writing conditions to be used in the if/else blocks and while loops.

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

## Conditionals (If/Else)
One of the most frequently-used component of any programming language is the conditional statement. This allows you run certain code blocks based on whether a certain set of conditions are true.

In an if/elif//else block, the *first* block of code where the condition is `True` is run, and the rest of the block is skipped. For example, if the `if` statement is `True`, then any `elif` or `else` blocks will be skipped even if the conditions are true.

The syntax of conditional blocks is as follows:

```python
if (condition1):
  # code run if condition1 is True
elif (condition2):
  # code run if condition2 is True and condition1 is False
else:
  # code run if neither condition1 or condition2 is True

```

```python
weather = 'cloudy'
if weather == 'cloudy':
  print('Wow look at the clouds!')
elif weather == 'sunny':
  print('It is so bright!')
else:
  print('Today is a good day.')

# prints 'Wow look at the clouds!'

```

## For Loops
*For* loops are great for looping a *specific* amount of times. Using a *for* loop in order to solve a problem is called *iteration*.

On the first line of the *for* loop, you define a variable and tell Python what the variable should equal when the loop runs. For example:

```python
for x in [1, 2, 3]:
  print(x)

"""
prints:
1
2
3
"""
```

Note that `x` changes value every time the *for loop* runs. This makes it so that you can perform consecutive operations on a variable outside the *for loop*. If you want to do the following operation: `1+2+3+4+5+...+99`, you can implement it as so:

```python
answer = 0
for x in range(1, 100, 1):
    answer = answer + x
print(answer) # prints 4950
```

You may have noticed that instead of hand typing a list to iterate through (`[1, 2, 3, 4, 5, ..., 100`), we used the `range` function. Let's talk about what `range` does.

## The mighty range() function
`range(start, stop, step)`

The `range` function is a special function called a *generator*. You can use `range` to generate a list of numbers to iterate through. For example, if we want to count down a rocket launch "5, 4, 3, 2, 1, Blastoff!", we can use the range function:

```python
for x in range(5, 0, -1):
    print(x)
print("Blastoff!")
```

In this case, the start number is `5`, because the first number we want range to assign to `x` is 5. The step is `-1`, because we want to subtract 1 every time the code loops back. And the stop is `0`, because when range reaches `0`, we want it to stop *and not execute the for loop*. This means that the countdown is inclusive of the start number and exclusive of the stop number.

How would we count all the numbers evenly divisible by 3 from 0 to 100 inclusive? Well we know that if we count by threes (`3, 6, 9, 12, ...`), all the numbers will be divisble by 3. So our start will be `0`, our stop will be `101`, and our step will be `3`.

You can see what our counter does here:

```python
for x in range(0, 101, 3):
    print(x)
"""
prints:
0
3
6
9
12
...
99
"""
```

And we can count all the print statements by adding to a counter outside the *for loop*:

```python
counter = 0
for x in range(0, 101, 3):
    counter = counter + 1
print(counter) # prints 34
```

## While Loops
*While loops*, similar to *for loops*, allow you to run lines of code repeatedly. However, instead of knowing how many times your code will loop, *while loops* are useful for looping infinitely as long as a certain condition is met. The syntax for a while loops:

```python
while (condition):
    # code to loop while condition is true
```

If you wanted to loop until the user presses the `q` button to exit, you could code it like this:

```python
val = input('Press q to exit')
while (val != 'q'):
  val = input('Press q to exit')
print('You exited the program!')
```

The print statement on the last line does not run until the *while* loop terminates. 

You also can implement a countdown with a while loop:
```python
number = 5
while number > 0:
  print(number)
  number = number - 1
print('Blastoff!')

"""
prints:
5
4
3
2
1
Blastoff!
"""
```

## Functions and Writing Modular Code
By now, we have explained the basics of what you need to know to code most things in Python. We left off some more complex topics, which we will highlight at the end along with good resources to learn them yourself.

Functions are a way of writing code that can be used in more than one place. It is often very helpful to break down your code so that it is more readable and easier to maintain and fix. 

Just like in math, functions take a certain input and give you an output. You can have multiple inputs, called *parameters*, and generate an output by *returning* data.

Here's a simple example:
```python
def my_function(country_name):
    print('I am from ' + country_name)

my_function('America') # prints 'I am from America'
my_function('Jordan') # prints 'I am from Jordan'
```

In the first line, the `def my_function(country_name):` indicates that you are defining a function called `my_function` that takes a single parameter named `country_name`. That means that within the function block, you can use the variable `country_name` to reference whatever string the function was called with.

Inside the function body, we print a message concatenated with the country_name passed in. Once again, notice that we use the variable country_name that is not assigned anywhere else except in the function definition.

In the last two lines, we *call* the function with the country_name `'America'` and `'Jordan'`. It then prints the message with the given country_name.

We have not talked about returning data from within a function yet, but this documentation will be updated for tomorrow.