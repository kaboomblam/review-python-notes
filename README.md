# Introduction

Python is a programming language developed by [Guido Von Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum). It is a high-level, general purpose programming language.

Fast to learn, most widely used for **Data Science, AI and Machine Learning**. In computer programming there are **Compiled Languages** and **Interpreted Languages**. Python is an interpreted language, a program called the *python interpreter*, goes through the code line by line to translate human-readable code to machine-readable code. [Learn more about Compiled and Interpreted Languages - FreeCodeCamp](https://www.freecodecamp.org/news/compiled-versus-interpreted-languages/).

> If you simply want to practice the basics, start at [Basics](#Basics).
# Setup New Project

> **Requirements**:
> - Need familiarity with the **command line**, learn how to use the command line [in this article](https://www.freecodecamp.org/news/how-to-use-the-cli-beginner-guide/)
> - Use [VSCode](https://code.visualstudio.com/) (optional)

1. Install Python: Download python from [python.org](https://www.python.org/)
> Ensure when installing you select `ADD TO PATH` option
>
> To ensure you have installed correctly, open command line and run command `python --version` if it shows version number then installation was done correctly.

2. Create an empty folder, (we are naming the folder **py-start**, however use any name you like), open folder in VSCode (read [this guide if unsure how](https://learn.microsoft.com/en-us/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions?view=vs-2022#:~:text=On%20the%20Visual%20Studio%20menu,link%20on%20the%20start%20window.)), using command line terminal in VSCode, create a new [Virtual Environment](#virtual-environment).
> Python programs access resources on your system, these resources are sometimes called **dependencies**, a virtual environment contains the resources to each python program rather than resources being shared across multiple python programs (system wide). This should help you share and manage python projects better.
>
> You'll learn more about this as you progress, for now copy the command below:

```python
python -m venv .venv
```

3. If you are using VSCode:
> - You may be prompted to install; **linter**, **code formatter** at different points.

Ensure that the correct python environment is selected in VSCode: Review [Docs on Environments in VSCode](https://code.visualstudio.com/docs/languages/python#_environments),

![](https://code.visualstudio.com/assets/docs/languages/python/selected-interpreter-status-bar.png)

In our case this should read `'.venv':venv` instead of `'base':conda`

⚠**Ensure to also Install Python Extensions:** 
- [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python),
- [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter).

# Basics
Some basics regarding the python language.

## Data Types & Variables

### Variables

A _variable_ in programming is a symbolic name that represents a value stored in the computer's memory. It's essentially a way to label and store data for later use.

#### Set a Variable
- The convention is to separate multiple words in a variable name with underscores: `hello_world = 'hello world'`

```python
hello = 'hello'
```
### Data Types

Variables can be of different data types, meaning they are storing that specific type of **data** in memory.

```python
i = 28 # interger
f = 2.8 # float
s = "String"
b = True # boolean
n = None 
```

### Arithmetic

```python
i = 1 + 1 # add
print(i) # 2
i = 1 / 1 # divide
print(i) # 1
i = 1 - 1 # subtract 
print(i) # 0
i = 1 * 1 # multiply
print(i) # 1
i = 5 ** 2 # power
print(i) # 25
```
### **Sequences** of data:
Python allows sequences of data to be used. They don't need to be of the same type explicitly

```python
name = "Sequence" # a word is a sequence of letters/characters
# to access an element in a sequence you variable_name[index]
# an index simply is the position in the sequence and begins from 0 not 1
# i.e.
print(name[0]) # will print 'S'
print(name[1]) # will print 'e'
print(name[2]) # will print 'q'
# and so on...
coords = (10, 0, 20.0) # tuple
```

> In python, we start counting from `0` not `1`, so the first element is `0`.

### List

- They are **mutable** meaning values can be changed:
```python
names = ["Alice", "Bob", "Charlie"] # list
```

#### How to Change a List value
```python
names = ["Alice", "Bob", "Charlie"] # list
names[0] = "Peter"
```

#### Append a List
```python
names = ["Alice", "Bob", "Charlie"] # list
names.append("Walker")
```
#### Extend a List
```python
names = ["Alice", "Bob", "Charlie"] # list
names.extend(["Norris", "Chuck"])
```
#### Pop a List
This removes last element:
```python
names = ["Alice", "Bob", "Charlie"] # list
names.pop() # pop last element
names.pop(1) # remove second element
```
### Tuple
- They are **immutable** meaning values can't be changed
```python
x = (0, 0, 2, 2)
```
#### Get element in a Tuple
```python
x = (0, 0, 2, 2)
print(x[0])
```

## **Collections**:
### Sets:
- All items are **unique**
```python
s = set()
s.add(1)
s.add(2)
s.add(2)
s.add(2)
print(s)
```
### Dictionaries:
- Collection of key-value pairs
```python
ages = {"Alice": 22, "Bob": 27}
ages["Alice"] += 1
print(ages)
```

# Configuration and tricks
Some few helpful tips and tricks generally in python.

## http server

Start a simple http server:

```py
python -m http.server --cgi 8360
```

## VSCode

If you have [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) extension installed you can run python interactively with the `#%%`:

```python
#%%
msg = "Hello World"
print(msg)

#%%
msg = "Hello again"
print(msg)
```

Run will appear above `#%%`.
## REPL
You call REPL in the command line for python by calling file with flag `i`
`python -i my_file.py`
## Virtual Environment

```powershell
python -m venv .venv
```

### Activate Virtual Env
-   **On Unix or MacOS, using the bash shell:** `source /path/to/venv/bin/activate`
-   **On Unix or MacOS, using the csh shell:** `source /path/to/venv/bin/activate.csh`
-   **On Unix or MacOS, using the fish shell:** `source /path/to/venv/bin/activate.fish`
-   **On Windows using the Command Prompt:** `path\to\venv\Scripts\activate.bat`
-   **On Windows using PowerShell:** `path\to\venv\Scripts\Activate.ps1`

## Matplotlib

```powershell
pip install matplotlib
```

## Operating System and File Related

```python
import os

print(os.getcwd()) # current directory
print(os.chdir('/path/')) # change directory
print(os.listdir()) # lists files and folder, can accept path as an arguement

# dirs
os.mkdir('Folder') # doesn't create all dirs in path Folder/Folder-Inside/Folder
os.mkdirs('Folder') # does create all them
os.rmdir('Folder') # doesnt delete top level directories, removes EMPTY dir
os.removedirs('Folder') # deletes directories recursively

# files
os.remove('file_path/file.txt')

# read file `os.scandir`
for filename in os.scandir(parsed.output_dir):
    print(filename)
    # filename.path
    # filename.name
    if filename.is_file():
		...
	elif filename.is_dir():
		...


# rename
os.rename('old_name.py', 'new_name.py')

# print contents
os.stat('text.txt') # file info, last modified and so forth

# scan directory

with os.scandir(path) as it:
    for entry in it:
        if not entry.name.startswith('.') and entry.is_file():
            print(entry.name)
            # entry.path
            # entry.is_dir()
            # entry.is_file()
            

for dirpath, dirnames, filenames in os.walk(os.gtcwd()): # prints entire directory tree
	print("Current Path: ", dirpath)
	print("Current Directory: ", dirnames)
	print("Current Files: ", filenames)
	print()

# print environ variables
print(os.environ)
print(os.environ.get('NAME'))

# path
file_path = os.path.join(path_here, 'text.txt')

print(os.path.basename('/tmp/text.txt')) # basename is text.txt
print(os.path.dirname('/tmp/text.txt')) # /tmp
print(os.path.split('path/text.txt')) # both /tmp and text.txt

os.path.exists('/path/')
os.path.isdir('/path/')
os.path.isfile('/path/')
print(os.path.splitext('path/text.txt')) # both /tmp/text and .txt
```

## Print statement
```python
print('Hello world')
print('Many things', 'printed', 5) # Many things printed 5
```

## Comprehensions
> Ways to easily construct a list
```python
x = [x for x in range(5)] # [0, 1, 2, 3, 4]
x = [x + 5 for x in range(5)] # [5, 6, 7, 8, 9, 10]
x = [0 for x in range(5)] # [0, 0, 0, 0, 0]

x = [x for x in range(0, 10, 2)] # [0, 2, 4, 6, 8]
```

> When we do a complex comprehension as below, the list [] is the **variable**
```python
x = [[i for i in range(5)] for x in range(10)]
```

> You can also use **dictionaries**.

```python
x = [{i for i in range(5)} for x in range(10)]
```

> Tuples
```python
x = tuple({i for i in range(5)} for x in range(10))
```

> If statements

```py
x = [i for i in range(10) if i % 2 == 0]
```

## Get User Input
```python
name = input('Name: ')
print('Hello', name)
```

## Strings
```python
a = "Hello"
a_multiline = """Lorem ipsum dolor sit amet,  
consectetur adipiscing elit,  
sed do eiusmod tempor incididunt  
ut labore et dolore magna aliqua."""

a_array = "Hello, World!"  
print(a[1])
```

### Slicing
```python
a = "Hello, World!"  
print(a[1])
```

Negative index:

```python
b = "Hello, World!"  
print(b[-5:-2])
```

### String Important Methods
```python
a = "Hello, World!"  
print(len(a))

a.replace("H", "J")

print(a.split(",")) # returns ['Hello', ' World!']

txt = "The rain in Spain stays mainly in the plain"

x = "ain" in txt
```



### Concatenation
```python
a = "Hello"  
b = "World"  
c = a + b
```

### Format string
- Old school way before python 3
```py
age = 36  
txt = "My name is John, and I am {}"  
print(txt.format(age))
```

```py
quantity = 3  
itemno = 567  
price = 49.95  
myorder = "I want {} pieces of item {} for {} dollars."  
print(myorder.format(quantity, itemno, price))
```

```py
myorder2 = "I want to pay {2} dollars for {0} pieces of item {1}."  
print(myorder2.format(quantity, itemno, price))
```

Or better yet in the **newer version**:
```python
name = "John"
print(f"Hello, {name}")
```

## Sliced
- Can slice a collection
- Uses **start:stop:step**
- stop means do not include
```python
x = [0, 1, 2, 3, 4, 5]
y = ["hi", "hello", "bye"]
z = 'hello'
tup = (1, 2, 3, 4, 5)

sliced = x[0:2:1] # start 0, stop 2, step 1 (optional since 1)
sliced2 = x[:2] # stop 2
sliced3 = x[1:] # start 1
sliced4 = x[3:1:-1] # step negative
sliced5 = x[::-1] # reverses list basically
```
## Control Flow
 ### if statement
 ```python
 x = 28
 
 if x > 0:
 	...
elif x < 0:
	...
else:
	...
```

### Range
- Range is non inclusive of number, ends before number
Can include **start**, **stop**, **step**:

```python
for i in range(1, 5): # just start and stop
	print(i)
```

Can even use negative
```python
for i in range(10, -1, -1):
	print(i)
```

### For loop
```python
for i in range(5):
	print(i)
```

```python
letters = ["A", "B", "C"]

for name in names:
	print(name)
```

### Loop a List

```python
for i in [1, 2, 3, 4]:
	print(i)
```

### Enumerate

```python
for i, v in enumerate([1, 2, 3, 4]):
	print(i, v)
```

### While
```python
while True:
	...
	
while i < 10:
	if i == 10:
		break
```

## Conditionals
### `or` and `not`
```python
result = (1 + 2 < 3) or not (5 x 5 == 10)
```

### `and`
```python
result = 1 + 1 == 2 and 5 + 5 == 10
```

## Imports
```python
from functions import square
```

# Enum
```python
from enum import Enum     # for enum34, or the stdlib version
# from aenum import Enum  # for the aenum version
Animal = Enum('Animal', 'ant bee cat dog')

Animal.ant  # returns <Animal.ant: 1>
Animal['ant']  # returns <Animal.ant: 1> (string lookup)
Animal.ant.name  # returns 'ant' (inverse lookup)
```

or

```python
class Animal(Enum):
    ant = 1
    bee = 2
    cat = 3
    dog = 4
```

# if `__main__`
```python
if __name__ == "__main__":
	main()
```

# Functions
```python
def say_hello():
	print("Hello")

say_hello()
```

> **pass**
```python
def func():
	pass
```

> With **params**:
```python
def say_hello(say):
	print(say)

say_hello("Hello")
```

> **Return**:
```python
def func(x):
	return x

def func2(x, y):
	return x * y, y * x # returns tuple (_,_)
	
r1, r2 = func2(5, 8)
```

> **Within functions**:
```python
def func():
	print('Function outer')
	def func():
		print("Function inner")
```

> **Optional** parameters

```python
def func(x, y, z=None):
	print('Func: ', x, y, z)
```

# Upack, \*args and \*\*kwargs 
> List uses \*
```python
def func(x, y):
	print(x, y)

pairs = [(1, 2), (3, 4)]

for pair in pairs:
	func(*pair)

```

> **Dictionary** uses \*\*. Name the arguments as the keys
```python
def func(x, y):
	print(x, y)
	
func(**{'x': 3, 'y': 5})
```

> args and kwargs
```python
def func(*args, **kwargs):
	print(args, kwargs)

func(1, 2, 3, 4, 5, one=1, two=2) # returns tuple
```

# Classes and OOP

- Create a new data type basically, or a blueprint for creating instances
- Methods are functions associated with a class
- Attributes are associated with the class

### Instances
```python
class Employee:
	pass

emp_1 = Employee()
```


### Instance Variables

One way to add instance variables:
```python
class Employee:
	pass

emp_1.first = "John"
emp_1.email = "joh@mailspell.com"

print(emp_1.email)
```

Better way:
```python
class Employee:
	def __init__(self, first, mail, pay):
		self.first = first
		self.mail = mail
		self.pay = pay

emp_1 = Employee('John', "john@mailspell.com", 50000)
```

### Class Methods
- If you need to access instance variables, then always start with **self**
```python
class Employee:
	def __init__(self, first="John", last="Doe", mail="jd@m.com", pay=10000):
		self.first = first
		self.mail = mail
		self.last = last
		self.pay = pay
	def fullname(self):
		return "{} {}".format(self.first, self.last)
```

### Class Variables
- Shared across all instances:
```python
class Employee:
	raise_amt = 1.04
	def __init__(self, first, mail, pay):
		self.first = first
		self.mail = mail
		self.pay = pay
	def apply_raise(self):
		self.pay = int(self.pay * Employee.raise_amt)
```

### Class Methods
```python
class Employee:
	def __init__(self):
		pass
	
	@classmethod
	def set_raise_amt(cls):
		pass
```

### Static Methods
- They have some logical connection to the class (return whether is workday from Employee class)

```python
class Employee:
	def __init__(self):
		pass
	
	@staticmethod
	def is_workday(day):
		pass
```

# Files
## Open
```python
with open('test.txt', 'r') as f: # w - write, a - append, r - read, r+ - read and write
	f_contents = f.read() # better for small files, entire contents
	f_contents = f.read(100) # better for larger files, each instance picks up from where the last stopped
	f_contents = f.readlines() # still small files
	f_contents = f.readline() # prints line by line each call
	print(f_contents)

	for line in f: # better for larger files
		print(line, end="") # just add end if `\n` end character

# f.close() # not needed if using context manager (the with block)
```

## Seek
```python
f.read()

f.seek(0) # restart from zero-th position

f.read() # prints from start
```

## Write
> **Careful:** w will overwrite a file if it exists, and also create the file if it doesn't exist.
```python
with open('test.txt', 'w') as f:
	f.write('Test\n')
	f.write('Write More')
```
