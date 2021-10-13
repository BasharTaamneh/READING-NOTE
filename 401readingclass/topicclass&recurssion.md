# Topic

## Classes and Objects

* Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

A very basic class would look something like this:

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
    
```

## Accessing Object Variables

To access the variable inside of the newly created object "myobjectx" you would do the following:

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.variable
    
```

**So for instance the below would output the string "blah":**

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

print(myobjectx.variable)
    
```

* You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class. For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)
    
```

## Accessing Object Functions

* To access a function inside of an object you use notation similar to accessing a variable:

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()

myobjectx.function()
```

*The above would print out the message, **"This is a message inside the class."***

```python
# define the Vehicle class
class Vehicle:
    name = ""
    kind = "car"
    color = ""
    value = 100.00
    def description(self):
        desc_str = "%s is a %s %s worth $%.2f." % (self.name, self.color, self.kind, self.value)
        return desc_str


car1 = Vehicle()
car1.name = "Fer"
car1.color = "red"
car1.kind = "convertible"
car1.value = 60000.00

car2 = Vehicle()
car2.name = "Jump"
car2.color = "blue"
car2.kind = "van"
car2.value = 10000.00

# test code
print(car1.description())
print(car2.description())

# output____________________

<script.py> output:
     is a  car worth $100.00.
     is a  car worth $100.00.

<script.py> output:
    Fer is a red convertible worth $60000.00.
    Jump is a blue van worth $10000.00.

```

## *Thinking Recursively in Python*

![Python](https://files.realpython.com/media/fixing_problems.ffd6d34e887e.png)

### Dear Pythonic Santa Claus…

* I realize that as fellow Pythonistas we are all consenting adults here, but children seem to grok the beauty of recursion better. So let’s not be adults here for a moment and talk about how we can use recursion to help Santa Claus.

* Have you ever wondered how Christmas presents are delivered? I sure have, and I believe Santa Claus has a list of houses he loops through. He goes to a house, drops off the presents, eats the cookies and milk, and moves on to the next house on the list. Since this algorithm for delivering presents is based on an explicit loop construction, it is called an iterative algorithm.

![](https://files.realpython.com/media/santa_claus_2.ecbf2686f1a1.png)

The algorithm for iterative present delivery implemented in Python:

```python
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

def deliver_presents_iteratively():
    for house in houses:
        print("Delivering presents to", house)
# output_______________
>>> deliver_presents_iteratively()
Delivering presents to Eric's house
Delivering presents to Kenny's house
Delivering presents to Kyle's house
Delivering presents to Stan's house

```

* But I feel for Santa. At his age, he shouldn’t have to deliver all the presents by himself. I propose an algorithm with which he can divide the work of delivering presents among his elves:

1. Appoint an elf and give all the work to him
2. Assign titles and responsibilities to the elves based on the number of houses for which they are responsible:
    1. >">" 1 He is a manager and can appoint two elves and divide his work among them
    2. > "=" 1 He is a worker and has to deliver the presents to the house assigned to him


![](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/elves_7.8d1af1cd85c8.png&w=1918&sig=24bad525e070e8248cc8fcce28fc3f52c68a69f9)

This is the typical structure of a recursive algorithm. If the current problem represents a simple case, solve it. If not, divide it into subproblems and apply the same strategy to them.

The algorithm for recursive present delivery implemented in Python:

```python
houses = ["Eric's house", "Kenny's house", "Kyle's house", "Stan's house"]

# Each function call represents an elf doing his work 
def deliver_presents_recursively(houses):
    # Worker elf doing his work
    if len(houses) == 1:
        house = houses[0]
        print("Delivering presents to", house)

    # Manager elf doing his work
    else:
        mid = len(houses) // 2
        first_half = houses[:mid]
        second_half = houses[mid:]

        # Divides his work among two elves
        deliver_presents_recursively(first_half)
        deliver_presents_recursively(second_half)
# output______________________

    >>> deliver_presents_recursively(houses)
    Delivering presents to Eric's house
    Delivering presents to Kenny's house
    Delivering presents to Kyle's house
    Delivering presents to Stan's house
```
![](https://files.realpython.com/media/stack.9c4ba62929cf.gif)

# Recursive Data Structures in Python

```python
attach_head(1,                                                  # Will return [1, 46, -31, "hello"]
            attach_head(46,                                     # Will return [46, -31, "hello"]
                        attach_head(-31,                        # Will return [-31, "hello"]
                                    attach_head("hello", [])))) # Will return ["hello"]

# output______________________

[1, 46, -31, 'hello']
```
![](https://files.realpython.com/media/list.3df62a89243d.gif)

