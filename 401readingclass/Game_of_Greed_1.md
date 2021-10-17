# Game_of_Greed

## ow to use the Random Module in Python?

**When to use it?**
We want the computer to pick a random number in a given range Pick a random element from a list, pick a random card from a deck, flip a coin etc. When making your password database more secure or powering a random page feature of your website.

The Random module contains some very useful functions.

- Randint

> If we wanted a random integer, we can use the randint function Randint accepts two parameters: a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.

```python
import random
print random.randint(0, 5)

#This will output either 1, 2, 3, 4 or 5.
```

- Random

If you want a larger number, you can multiply it.

For example, a random number between 0 and 100:

```python
import random
random.random() * 100
```

- Choice
  
Generate a random value from the sequence sequence.

random.choice( ['red', 'black', 'green'] ).
The choice function can often be used for choosing a random element from a list.

```python
import random

myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]

random.choice(myList)
```

- Shuffle
  
The shuffle function, shuffles the elements in list in place, so they are in a random order.

```python
from random import shuffle
    x = [[i] for i in range(10)]
    shuffle(x)

Output:_____

# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]

# of course your results will vary
```

- Randrange
  
Generate a randomly selected element from range(start, stop, step)
random.randrange(start, stop[, step])

```python
import random

for i in range(3):
    print random.randrange(0, 101, 5)
```

## Why use Risk Analysis?

- In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

- Now, you might think what could be the possible risks that you could encounter? Well here is a list:
  
> Use of new hardware

> Use of new technology

> Use of new automation tool

> The sequence of code

> Availability of test resources for the application

- Now, you must know there are certain risks that are unavoidable. I am enumerating them below:

1. The time that you allocated for testing
2. A defect leakage due to the complexity or size of the application
3. Urgency from the clients to deliver the project
4. Incomplete requirements

- In such cases, you have to tackle the situation with
  
   > care. Following points can be taken care of:

   > Conduct Risk Assessment review meeting

   > Use maximum resources to work on high-risk areas

   > Create a Risk Assessment database for future use

   > Identify and notice the risk magnitude indicators: high, medium, low.

***Risk Assessment***
* In the risk analysis process, these steps prove to be the most important one. It is said that this step is way too complex and should be tackled with the utmost care. After risk identification, assessment has to be dealt programmatically. There are a few perspectives on risk assessment. Read on!

![](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2019/08/Picture1-528x290.png)

Moving on! Our next topic on Risk Analysis in Software Testing