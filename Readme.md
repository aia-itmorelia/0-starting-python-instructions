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
To install the latest Python version, above 3.8, use the next commands in the terminal to let the *APT* package manager to install it:

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
In the MacOS system there is recommended package manager call *Homebrew*, to install it run the next command in the terminal:
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

# `if`, `for` and plot
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
# References

[^1]: https://developers.google.com/edu/python/introduction
