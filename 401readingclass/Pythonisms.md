# Pythonisms

## Enriching Your Python Classes With Dunder (Magic, Special) Methods

### What Are Dunder Methods?

In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example` __init__ or __str__`.

As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

These “dunders” or “special methods” in Python are also sometimes called “magic methods.” But using this terminology can make them seem more complicated than they really are—at the end of the day there’s nothing “magical” about them. You should treat these methods like a normal language feature.

Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:

```py
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```

```py
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```

Another example is slicing. You can implement a` __getitem__ `method which allows you to use Python’s list slicing syntax: `obj[start:stop]`.

## Special Methods and the Python Data Model


This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. If you want to write more Pythonic code, knowing how and when to use dunder methods is an important step.

For a beginner this might be slightly overwhelming at first though. No worries, in this article I will guide you through the use of dunder methods using a simple Account class as an example.

## Enriching a Simple Account Class

Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

> Initialization of new objects

> Object representation

> Enable iteration

> Operator overloading (comparison)

> Operator overloading (addition)

> Method invocation

> Context manager support (with statement)

You can find the final code example here. I’ve also put together a Jupyter notebook so you can more easily play with the examples.


[Dunder (Magic, Special) Methods](https://dbader.org/blog/python-dunder-methods)



# Python Iterators: A Step-By-Step Introduction

* Understanding iterators is a milestone for any serious Pythonista. With this step-by-step tutorial you’ll understanding class-based iterators in Python, completely from scratch.

I love how beautiful and clear Python’s syntax is compared to many other programming languages.

Let’s take the humble for-in loop, for example. It speaks for Python’s beauty that you can read a Pythonic loop like this as if it was an English sentence:

```py
numbers = [1, 2, 3]
for n in numbers:
    print(n)
```

* But how do Python’s elegant loop constructs work behind the scenes? How does the loop fetch individual elements from the object it is looping over? And how can you support the same programming style in your own Python objects?

You’ll find the answer to these questions in Python’s iterator protocol:

> Objects that support the `__iter__` and `__next__` dunder methods automatically work with for-in loops.


But let’s take things step by step. Just like decorators, iterators and their related techniques can appear quite arcane and complicated on first glance. So we’ll ease into it.

In this tutorial you’ll see how to write several Python classes that support the iterator protocol. They’ll serve as “non-magical” examples and test implementations you can build upon and deepen your understanding with.

We’ll focus on the core mechanics of iterators in Python 3 first and leave out any unnecessary complications, so you can see clearly how iterators behave at the fundamental level.

I’ll tie each example back to the for-in loop question we started out with. And at the end of this tutorial we’ll go over some differences that exist between Python 2 and 3 when it comes to iterators.

Ready? Let’s jump right in!

## Python Iterators That Iterate Forever


* We’ll begin by writing a class that demonstrates the bare-bones iterator protocol in Python. The example I’m using here might look different from the examples you’ve seen in other iterator tutorials, but bear with me. I think doing it this way gives you a more applicable understanding of how iterators work in Python.

Over the next few paragraphs we’re going to implement a class called Repeater that can be iterated over with a for-in loop, like so:

```py
repeater = Repeater('Hello')
for item in repeater:
    print(item)
```

- Like its name suggests, instances of this Repeater class will repeatedly return a single value when iterated over. So the above example code would print the string Hello to the console forever.

To start with the implementation we’ll define and flesh out the Repeater class first:

```py
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return RepeaterIterator(self)
```
- On first inspection, Repeater looks like a bog-standard Python class. But notice how it also includes the `__iter__` dunder method.

What’s the RepeaterIterator object we’re creating and returning from `__iter__`? It’s a helper class we also need to define for our for-in iteration example to work:

```py
class RepeaterIterator:
    def __init__(self, source):
        self.source = source

    def __next__(self):
        return self.source.value
```




Again, RepeaterIterator looks like a straightforward Python class, but you might want to take note of the following two things:

In the `__init__` method we link each RepeaterIterator instance to the Repeater object that created it. That way we can hold on to the “source” object that’s being iterated over.

In RepeaterIterator.`__next__`, we reach back into the “source” Repeater instance and return the value associated with it.

In this code example, Repeater and RepeaterIterator are working together to support Python’s iterator protocol. The two dunder methods we defined, `__iter__` and `__next__`, are the key to making a Python object iterable.

We’ll take a closer look at these two methods and how they work together after some hands-on experimentation with the code we’ve got so far.

Let’s confirm that this two-class setup really made Repeater objects compatible with for-in loop iteration. To do that we’ll first create an instance of Repeater that would return the string 'Hello' indefinitely:

```py 
>>> repeater = Repeater('Hello')
```

And now we’re going to try iterating over this repeater object with a for-in loop. What’s going to happen when you run the following code snippet?

```py
>>> for item in repeater:
...     print(item)
```

Right on! You’ll see 'Hello' printed to the screen…a lot. Repeater keeps on returning the same string value, and so, this loop will never complete. Our little program is doomed to print 'Hello' to the console forever:

```
Hello
Hello
Hello
Hello
Hello
...
```

But congratulations—you just wrote a working iterator in Python and used it with a for-in loop. The loop may not terminate yet…but so far, so good!

Next up we’ll tease this example apart to understand how the `__iter__` and `__next__` methods work together to make a Python object iterable.

Pro tip: If you ran the last example inside a Python REPL session or from the terminal and you want to stop it, hit Ctrl + C a few times to break out of the infinite loop.

[Python Iterators](https://dbader.org/blog/python-iterators)




# What Are Python Generators?

* Generators are a tricky subject in Python. With this tutorial you’ll make the leap from class-based iterators to using generator functions and the “yield” statement in no time.

If you’ve ever implemented a class-based iterator from scratch in Python, you know that this endeavour requires writing quite a bit of boilerplate code.

And yet, iterators are so useful in Python: They allow you to write pretty for-in loops and help you make your code more Pythonic and efficient.

As a (proud) “lazy” Python developer, I don’t like tedious and repetitive work. And so, I often found myself wondering:

> If there only was a more convenient way to write these Python iterators in the first place…

Surprise, there is! Once again, Python helps us out with some syntactic sugar to make writing iterators easier.

In this tutorial you’ll see how to write Python iterators faster and with less code using generators and the yield keyword.

Ready? Let’s go!

[Python Generators](https://dbader.org/blog/python-generators)






