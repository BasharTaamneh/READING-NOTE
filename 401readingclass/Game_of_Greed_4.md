# Game_of_Greed_4

## Enriching Your Python Classes With Dunder (Magic, Special) Methods

**What Are Dunder Methods?**

- In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example ```__init__ or __str__.```

- As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

- These “dunders” or “special methods” in Python are also sometimes called “magic methods.” But using this terminology can make them seem more complicated than they really are—at the end of the day there’s nothing “magical” about them. You should treat these methods like a normal language feature.

- Dunder methods let you emulate the behavior of built-in types. For example, to get the length of a string you can call len('string'). But an empty class definition doesn’t support this behavior out of the box:

```py
class NoLenSupport:
    pass

>>> obj = NoLenSupport()
>>> len(obj)
TypeError: "object of type 'NoLenSupport' has no len()"
```
To fix this, you can add a __len__ dunder method to your class:
```py
class LenSupport:
    def __len__(self):
        return 42

>>> obj = LenSupport()
>>> len(obj)
42
```
- Another example is slicing. You can implement a ```__getitem__``` method which allows you to use Python’s list slicing syntax: ```obj[start:stop]```.

**Special Methods and the Python Data Model**

- This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

- You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. If you want to write more Pythonic code, knowing how and when to use dunder methods is an important step.

- For a beginner this might be slightly overwhelming at first though. No worries, in this article I will guide you through the use of dunder methods using a simple Account class as an example.

**Enriching a Simple Account Class**

Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

1. Initialization of new objects
2. Object representation
3. Enable iteration
4. Operator overloading (comparison)
5. Operator overloading (addition)
6. Method invocation6. 
7. Context manager support (with statement)

## Object Initialization: `__init__`

Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the `__init__`dunder:

```py
class Account:
    """A simple account class"""

    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []
```

## Object Representation: `__str__, __repr__`

> `__repr__`: The “official” string representation of an object. This is how you would make an object of the class. The goal of `__repr__` is to be unambiguous.

> `__str__`: The “informal” or nicely printable string representation of an object. This is for the enduser.


## Iteration: `__len__, __getitem__, __reversed__`

```py
# In order to iterate over our account object I need to add some transactions. So first, I’ll define a simple method to add transactions. I’ll keep it simple because this is just setup code to explain dunder methods, and not a production-ready accounting system:

def add_transaction(self, amount):
    if not isinstance(amount, int):
        raise ValueError('please use int for amount')
    self._transactions.append(amount)

# I also defined a property to calculate the balance on the account so I can conveniently access it with account.balance. This method takes the start amount and adds a sum of all the transactions:

@property
def balance(self):
    return self.amount + sum(self._transactions)

# Let’s do some deposits and withdrawals on the account:

>>> acc = Account('bob', 10)

>>> acc.add_transaction(20)
>>> acc.add_transaction(-10)
>>> acc.add_transaction(50)
>>> acc.add_transaction(-20)
>>> acc.add_transaction(30)

>>> acc.balance
80
```
---

>.
```markdown
## Basic Statistics in Python — Probability ##
```
>.
## What is probability?

- At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. In a coin toss the only events that can happen are:

> 1. Flipping a heads
> 2. Flipping a tails

- These two events form the sample space, the set of all possible events that can happen. To calculate the probability of an event occurring, we count how many times are event of interest can occur (say flipping heads) and dividing it by the sample space. Thus, probability will tell us that an ideal coin will have a 1-in-2 chance of being heads or tails. By looking at the events that can occur, probability gives us a framework for making predictions about how often events will happen. However, even though it seems obvious, if we actually try to toss some coins, we’re likely to get an abnormally high or low counts of heads every once in a while. If we don’t want to make the assumption that the coin is fair, what can we do? We can gather data! We can use statistics to calculate probabilities based on observations from the real world and check how it compares to the ideal.

## From statistics to probability

- Our data will be generated by flipping a coin 10 times and counting how many times we get heads. We will call a set of 10 coin tosses a trial. Our data point will be the number of heads we observe. We may not get the “ideal” 5 heads, but we won’t worry too much since one trial is only one data point. If we perform many, many trials, we expect the average number of heads over all of our trials to approach the 50%. The code below simulates 10, 100, 1000, and 1000000 trials, and then calculates the average proportion of heads observed. Our process is summarized in the image below as well.

![](https://i.imgur.com/GtbawRt.jpg)

```py
import random
def coin_trial():
heads = 0
for i in range(100):
if random.random() <= 0.5:
heads +=1
return headsdef simulate(n):
trials = [] for i in range(n):
trials.append(coin_trial())
return(sum(trials)/n)
simulate(10)
>>> 5.4
simulate(100)
>>> 4.83
simulate(1000)
>>> 5.055
simulate(1000000)
>>> 4.999781
```

![](https://i.ytimg.com/vi/f26vt5uQ_uI/hqdefault.jpg)

## Conclusion

* We started with descriptive statistics and then connected them to probability. From probability, we developed a way to quantatively show if two groups come from the same distribution. In this case, we compared two wine recommendations and found that they most likely do not come from the same score distribution. In other words, one wine type is most likely better than the other one. Statistics doesn’t have to be a field relegated to just statisticians. As a data scientist, having an intuitive understanding on common statistical measures represent will give you an edge on developing your own theories and the ability to subsequently test these theories. We barely scratched the surface of inferential statistics here, but the same general ideas here will help guide your intuition in your statistical journey. Our article discussed the advantages of the normal distribution, but statisticians have also developed techniques to adjust for distributions that aren’t normal.