# Game_of_Greed_3

## List Comprehensions in Python

### **Create a List with range()**

- Let’s start by creating a list of numbers using Python list comprehensions. We’ll take advantage of Python’s **range()** method as a way to create a list of digits.

**Example 1: Creating a list with list comprehensions**

```python
# construct a basic list using range() and list comprehensions
# syntax
# [ expression for item in list ]
digits = [x for x in range(10)]

print(digits)

Output____

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### **Create a List Using Loops and List Comprehension in Python**

- To better illustrate how a list comprehension can be used to write more efficient Python code, we’ll take a look at a side by side comparison. 

In the following example, you’ll see two different techniques for creating a Python list. The first is a for loop. We’ll use it to construct a list of the powers of two.

**Example 2: Comparing list creation methods in Python**

First, create a list and loop through it. Add an expression, in this example, we’ll raise x to the power of 2.


```python
# create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
Output___
# The same thing can be done using a list comprehension, but with a fraction of the code. Let’s take a look at how to create a list of squares using the list comprehension method.
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
# Even in this basic example, it’s obvious that list comprehensions reduce the code necessary to complete rather complicated task when working with a list.
```

### **Multiplying Parts of a List**

- What if we wanted to multiply every number in a list by three in Python? We could write a for loop and store the results in a new list, or we could use list comprehensions.

**Example 3: Multiplication with list comprehensions**

```python
# create a list with list comprehensions
multiples_of_three = [ x*3 for x in range(10) ]

print(multiples_of_three)
Output

[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]

# By taking advantage of list comprehensions, it’s possible to work on only part of a list. For instance, if you only wanted the even numbers in a given range, you could find them using a filter.

# Adding a filter to the list comprehension allows for greater flexibility. By using filters, we can select certain items from the list, while excluding others. This is an advanced feature of lists in Python.

even_numbers = [ x for x in range(1,20) if x % 2 == 0]

Output______

[2, 4, 6, 8, 10, 12, 14, 16, 18]
```
### **Show the first letter of each word using Python**


- So far we’ve seen examples of building a list of numbers in Python. Next, let’s try working with strings and the various ways list comprehensions can be used to elegantly handle a list of strings.

**Example 4: Using list comprehensions with strings**

```python
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)

Output___

['E', 'L', 'F', 'T', 'E', 'S']

# List comprehensions can make solving issues involving strings much easier using simplified expressions. These methods can save time and precious lines of code.
```

## In conclusion

* Hopefully you’ve seen the potential of list comprehensions and how they can be used to write more elegant Python code. Writing compact code is essential for maintaining programs and working with teams. 

* Learning to make use of advanced features like list comprehension will save time and improve productivity. 

* Not only will your colleagues thank you when your Python code is more concise and easier to read, but you’ll thank yourself when you come back to a program you haven’t worked on in months and the code is manageable.