# 1. Introduction to Python

Python is a dynamic, interpreted (bytecode-compiled) language. There are no type declarations of variables, parameters, functions, or methods in source code. This makes the code short and flexible, and you lose the compile-time type checking of the source code. Python tracks the types of all values at runtime and flags code that does not make sense as it runs[^1].

Actually, Python is widely used by engineers, scientists, statistics and data-science. Why should I learn Python?

- Well, is a free and open source,
- is versatile (multiparadign)
- is portable and usable in other platforms
- There are several modules to work with

# Installing python

**Note**: this guide only focus on GNU/Linux Ubuntu and Unix based (MacOS) operate systems (OS).

## Ubuntu

To install the latest Python version, above 3.8, use the next commands in the terminal to let the _APT_ package manager to install it:

```
sudo apt update
sudo apt install python3
```

we are going to use the Integrated Development Environment (IDLE), thus, please run the next commands to install it:

```
sudo apt-get update
sudo apt-get install idle3
```

## Unix-based

In the MacOS system there is recommended package manager call _Homebrew_, to install it run the next command in the terminal:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

then, you will have access to the `brew` command to install and manage your packages. Next, you can install Python by using:

```
brew install python3 python-tk
```

these both packages allow us to run the IDLE for Python.

# Testing Python

## Interactive

```
$ python        ## Run the Python interpreter
Python 3.X.X (XXX, XXX XX XXXX, 03:41:42) [XXX] on XXX
Type "help", "copyright", "credits" or "license" for more information.
>>> a = 6       ## set a variable in this interpreter session
>>> a           ## entering an expression prints its value
6
>>> a + 2
8
>>> a = 'hi'    ## 'a' can hold a string just as well
>>> a
'hi'
>>> len(a)      ## call the len() function on a string
2
>>> a + len(a)  ## try something that doesn't work
Traceback (most recent call last):
  File "", line 1, in
TypeError: can only concatenate str (not "int") to str
>>> a + str(len(a))  ## probably what you really wanted
'hi2'
>>> foo         ## try something else that doesn't work
Traceback (most recent call last):
  File "", line 1, in
NameError: name 'foo' is not defined
>>> ^D          ## type CTRL-d to exit (CTRL-z in Windows/DOS terminal)
```

## module files

Python source files use the ".py" extension and are called "modules." With a Python module hello.py, the easiest way to run it is with the shell command "python hello.py Alice" which calls the Python interpreter to execute the code in hello.py, passing it the command line argument "Alice"

```

#!/usr/bin/env python

# import modules used here -- sys is a very standard one
import sys

# Gather our code in a main() function
def main():
    print('Hello there', sys.argv[1])
    # Command line args are in sys.argv[1], sys.argv[2] ...
    # sys.argv[0] is the script name itself and can be ignored

# Standard boilerplate to call the main() function to begin
# the program.
if __name__ == '__main__':
    main()
```

to run the code use

```
$ python hello.py Guido
Hello there Guido
$ ./hello.py Alice  ## without needing 'python' first (Unix)
Hello there Alice
```

# Jupyter Notebook

## Basic commands

Jupyter Notebook is widely used for data analysis. The notebooks documents are documents produced by the Jupyter Notebook App, which can contain both code (e.g. Python) and rich text elements (paragraphs, equations, links, etc.).

The Jupyter Notebook App is a client-server application that allows editing and running notebook documents by a browser.

### Shortcuts in both modes:

- Shift + Enter run the current cell, select below
- Ctrl + Enter run selected cells
- Alt + Enter run the current cell, insert below
- Ctrl + S save and checkpoint

### While in command mode (press Esc to activate):

**Enter take you into edit mode** and then the command that you need like change the cell type to Markdown:

- H show all shortcuts
- Up select cell above
- Down select cell below
- Shift + Up extend selected cells above
- Shift + Down extend selected cells below
- A insert cell above
- B insert cell below
- X cut selected cells
- C copy selected cells
- V paste cells below
- Shift + V paste cells above
- D, D (press the key twice) delete selected cells
- Z undo cell deletion
- S Save and Checkpoint
- Y change the cell type to Code
- M change the cell type to Markdown
- P open the command palette

This dialog helps you run any command by name. It’s really useful if you don’t know some shortcut or when you don’t have a shortcut for the wanted command.

- Shift + Space scroll notebook up
- Space scroll notebook down

### While in edit mode (press Enter to activate)

- Esc take you into command mode
- Tab code completion or indent
- Shift + Tab tooltip
- Ctrl + ] indent
- Ctrl + [ deindent //]
- Ctrl + A select all
- Ctrl + Z undo
- Ctrl + Shift + Z or Ctrl + Y redo
- Ctrl + Home go to cell start
- Ctrl + End go to cell end
- Ctrl + Left go one word left
- Ctrl + Right go one word right
- Ctrl + Shift + P open the command palette
- Down move cursor down
- Up move cursor up

# Basics of Python programming language

## `if`, `for` and plot

```
x = int(input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print('Negative changed to zero')
... elif x == 0:
...     print('Zero')
... elif x == 1:
...     print('Single')
... else:
...     print('More')
...
More
```

## for statement

```
words = ['cat', 'window', 'defenestrate']
for w in words:
  print(w, len(w))
```

```
for i in range(5):
  print(i)
```

```
a = ['Mary', 'had', 'a', 'little', 'lamb']

for i in range(len(a)):
  print(i, a[i])
```

## Numpy arrays

Numpy, on the other hand, is a core Python library for scientific computation (hence the name “Numeric Python” or Numpy). The library provides methods and functions to create and work with multi-dimensional objects called arrays. Arrays are grids of values, and unlike Python lists, they are of the same data type:

```
# 1-dimesional array
array([1, 2, 3])

# 2-dimensional array
array([[1, 2],
       [3, 4],
       [5, 6]])
```

```
import numpy as np
a = np.array([[1,2],[3,4],[5,6]])
```

## Matplotlib

Matplotlib is a 2d plotting library which produces publication quality figures in a variety of hardcopy formats and interactive environments. Matplotlib can be used in Python scripts, Python and IPython shell, Jupyter Notebook, web application servers and GUI toolkits.

matplotlib.pyplot is a collection of functions that make matplotlib work like MATLAB. Majority of plotting commands in pyplot have MATLAB analogs with similar arguments. Let us take a couple of examples:

```
import matplotlib.pyplot as plt
plt.plot([1,2,3,4])
plt.ylabel('some numbers')
plt.show()
```

```
import matplotlib.pyplot as plt
>>> x = [21,22,23,4,5,6,77,8,9,10,31,32,33,34,35,36,37,18,49,50,100]
>>> num_bins = 5
>>> plt.hist(x, num_bins, facecolor='blue')
>>> plt.show()
```

```
# how to crate functions
def myFuncion(x):
    y = np.sin(x)/np.cos(x)
    return y
```

```
import matplotlib.pyplot as plt
time = np.linspace(0,10)
y = myFuncion(time)
y2 = np.tan(time)
plt.plot(time, y/2,'-g*')
plt.plot(time, y2, ':m+')
plt.show()
```

## Subplots

A subplot for one column and three rows

```
plt.subplot(3,1,1)
plt.plot(time, np.sin(time),'r', label='$y_1$')
plt.legend()
plt.subplot(3,1,2)
plt.plot(time, np.cos(time),'g',label='y2')
plt.legend()
plt.subplot(3,1,3)
plt.plot(time, np.tan(time),'k', label='y3')
plt.legend()
plt.show()
```

A plot for three columns and two rows

```
plt.subplot(6,3,1)
plt.plot(time, np.sin(time),'r', label='y_1')
plt.subplot(6,3,2)
plt.plot(time, np.cos(time),'g',label='y2')
plt.subplot(6,3,3)
plt.plot(time, np.tan(time),'k', label='y3')
plt.subplot(6,3,4)
plt.plot(time, np.sin(time),'r', label='$y_1$')
plt.subplot(6,3,5)
plt.plot(time, np.cos(time),'g',label='y2')
plt.subplot(6,3,6)
plt.plot(time, np.tan(time),'k', label='$y_1$')
plt.show()
```

# References

[^1]: https://developers.google.com/edu/python/introduction
