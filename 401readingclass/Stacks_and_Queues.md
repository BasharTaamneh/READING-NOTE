# Stacks_and_Queues

## Stack

* In the pushdown stacks only two operations are allowed: push the item into the stack, and pop the item out of the stack. A stack is a limited access data structure - elements can be added and removed from the stack only at the top. push adds an item to the top of the stack, pop removes the item from the top. A helpful analogy is to think of a stack of books; you can remove only the top book, also you can add a new book on the top.

![](https://everythingcomputerscience.com/images/stackImg.jpg)

## Queue

* An excellent example of a queue is a line of students in the food court of the UC. New additions to a line made to the back of the queue, while removal (or serving) happens in the front. In the queue only two operations are allowed enqueue and dequeue. Enqueue means to insert an item into the back of the queue, dequeue means removing the front item. The picture demonstrates the FIFO access. The difference between stacks and queues is in removing. In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added.


![](https://everythingcomputerscience.com/images/queueImg.jpg)

## FIFO & LILO and LIFO & FILO *Principles*



> *Queue:* First In First Out (FIFO): The first object into a queue is the first object to leave the queue, used by a queue.

> *Stack:* Last In First Out (LIFO): The last object into a stack is the first object to leave the stack, used by a stack

**OR**

> *Stack:* Last In First Out (FILO): The First object or item in a stack is the last object or item to leave the stack.

> *Queue:* Last In First Out (LILO): The last object or item in a queue is the last object or item to leave the queue.

## stacks Code

```py

# Python program to
# demonstrate stack implementation
# using collections.deque
 
 
from Collections import deque
 
stack = deque()
 
# append() function to push
# element in the stack
stack.append('a')
stack.append('b')
stack.append('c')
 
print('Initial stack:')
print(stack)
 
# pop() function to pop
# element from stack in
# LIFO order
print('\nElements popped from stack:')
print(stack.pop())
print(stack.pop())
print(stack.pop())
 
print('\nStack after elements are popped:')
print(stack)
 
# uncommenting print(stack.pop()) 
# will cause an IndexError
# as the stack is now empty

# // Output: _________________________________

# Initial stack:
deque(['a', 'b', 'c'])

# Elements popped from stack:
c
b
a

# Stack after elements are popped:
deque([])
```
## Queue Code

```py
# Python program to
# demonstrate queue implementation
# using collections.dequeue
 
 
from collections import deque
 
# Initializing a queue
q = deque()
 
# Adding elements to a queue
q.append('a')
q.append('b')
q.append('c')
 
print("Initial queue")
print(q)
 
# Removing elements from a queue
print("\nElements dequeued from the queue")
print(q.popleft())
print(q.popleft())
print(q.popleft())
 
print("\nQueue after removing elements")
print(q)
 
# Uncommenting q.popleft()
# will raise an IndexError
# as queue is now empty
# Output: ______________________________
 

# Initial queue
deque(['a', 'b', 'c'])

# Elements dequeued from the queue
a
b
c

# Queue after removing elements
deque([])

```