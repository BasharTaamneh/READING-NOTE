# FileIO & Exceptions

## Reading and Writing Files in Python

**array-insert-shift**

* Files on most modern file systems are composed of three main parts:

![](https://files.realpython.com/media/FileFormat.02335d06829d.png)

**Header:** metadata about the contents of the file (file name, size, type, and so on)

**Data:** contents of the file as written by the creator or editor

**End of file (EOF):** special character that indicates the end of the file

**File Paths**

* When you access a file on an operating system, a file path is required. The file path is a string that represents the location of a file. It’s broken up into three major parts:

**Folder Path:** the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)

**File Name:** the actual name of the file

**Extension:** the end of the file path pre-pended with a period (.) used to indicate the file type

* Here’s a quick example. Let’s say you have a file located within a file structure like this:

```
/
│
├── path/
|   │
│   ├── to/
│   │   └── cats.gif
│   │
│   └── dog_breeds.txt
|
└── animals.csv
```

## Python Exceptions

* A Python program terminates as soon as it encounters an error. In Python, an error can be a syntax error or an exception. In this article, you will see what an exception is and how it differs from a syntax error. After that, you will learn about raising exceptions and making assertions. Then, you’ll finish with a demonstration of the try and except block.

![Python Exceptions](https://files.realpython.com/media/intro.8915db1758d8.png)

## Exceptions versus Syntax Errors

Syntax errors occur when the parser detects an incorrect statement. Observe the following example:

```python
>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
```

The arrow indicates where the parser ran into the syntax error. In this example, there was one bracket too many. Remove it and run your code again:

```python
>>> print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
```

* This time, you ran into an exception error. This type of error occurs whenever syntactically correct Python code results in an error. The last line of the message indicated what type of exception error you ran into.

* Instead of showing the message exception error, Python details what type of exception error was encountered. In this case, it was a ZeroDivisionError. Python comes with various built-in exceptions as well as the possibility to create self-defined exceptions.

## Raising an Exception

We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.

![Raising an Exception](https://files.realpython.com/media/raise.3931e8819e08.png)

If you want to throw an error when a certain condition occurs using raise, you could go about it like this:

```python
x = 10
if x > 5:
    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```

When you run this code, the output will be the following:

```python
Traceback (most recent call last):
  File "<input>", line 4, in <module>
Exception: x should not exceed 5. The value of x was: 10
```

* The program comes to a halt and displays our exception to screen, offering clues about what went wrong.

## The AssertionError Exception

* Instead of waiting for a program to crash midway, you can also start by making an assertion in Python. We assert that a certain condition is met. If this condition turns out to be True, then that is excellent! The program can continue. If the condition turns out to be False, you can have the program throw an AssertionError exception.

![](https://files.realpython.com/media/assert.f6d344f0c0b4.png)

## The try and except Block: Handling Exceptions

* The try and except block in Python is used to catch and handle exceptions. Python executes code following the try statement as a “normal” part of the program. The code that follows the except statement is the program’s response to any exceptions in the preceding try clause.

![](https://files.realpython.com/media/try_except.c94eabed2c59.png)

## The else Clause

* In Python, using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions.

![](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png)

## Cleaning Up After Using finally

* Imagine that you always had to implement some sort of action to clean up after executing your code. Python enables you to do so using the finally clause.

![](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)

**Summing Up**

1. raise allows you to throw an exception at any time.
2. assert enables you to verify if a certain condition is met and throw an exception if it isn’t.
3. In the try clause, all statements are executed until an exception is encountered.
4. except is used to catch and handle the exception(s) that are encountered in the try clause.
5. else lets you code sections that should run only when no exceptions are encountered in the try clause.
6. finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.
