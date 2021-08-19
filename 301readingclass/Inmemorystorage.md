# In memory storage

## What is a ‘call’?


The call stack maintains a record of the position of each stack frame. It knows the next function to be executed (and will remove it after execution). This is what makes code execution in JavaScript synchronous.

Think of yourself standing on a queue, in a grocery store cash point. You can only be attended to after the person in front of you have been attended to. That’s synchronous.

## How many ‘calls’ can happen at once?

Instead it is dependent on the memory available on the stack, which may ... instances that may not necessarily be dependent on one another.
In my experience, a stack overflow in Java is almost always due to a programming error. See 

## What does LIFO mean?

last in, first out (LIFO) is a method used to account for inventory. Under LIFO, the costs of the most recent products purchased (or produced) are the first to be expensed. LIFO is used only in the United States and governed by the generally accepted accounting principles (GAAP).


## Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

```javascript
 1: #include <stdio.h> 
 2: 
 3: int mogrify(int a, int b){
 4:   int tmp = a*4 - b / 3;                  // First line of mogrify (mogrify)
 5:   return tmp;                             // (mogrify_return)
 6: }
 7: double truly_half(int x){
 8:   double tmp = x / 2.0;                   // First line of turly_half (truly_half)
 9:   return tmp;                             // (truly_half_return)
10: }
11: int main(){
12:   int a = 7, y = 17;                      // First line of main (main)
13:   int mog = mogrify(a,y);                 // Call to mogrify (mogrify_call)
14:   printf("Done with mogrify\n");          // (first_print)
15: 
16:   double x = truly_half(y);               // Call to truly_half (truly_half_call)
17:   printf("Done with truly_half\n");       // (second_print)
18: 
19:   a = mogrify(x,mog);                     // (mogrify2)
20: 
21:   printf("Results: %d %lf\n",mog,x);      // (last_print)
22:   return 0;                               // (main_return)
23: }
//Compile and run
lila [stack-demo-code]% gcc simple_calls.c
lila [stack-demo-code]% ./a.out
Done with mogrify
Done with truly_half
Results: 23 8.500000
```
## What causes a Stack Overflow?

The most-common cause of stack overflow is excessively deep or infinite recursion, in which a function calls itself so many times that the space needed to store the variables and information associated with each call is more than can fit on the stack.

## What is a ‘refrence error’?

An #REF error (the “ref” stands for reference) is the message Excel displays when a formula references a cell that no longer exists, usually caused by deleting cells that a formula is referring to.


## What is a ‘syntax error’?


In computer science, a syntax error is an error in the syntax of a sequence of characters or tokens that is intended to be written in compile-time.

## What is a ‘range error’?

Description. A RangeError is thrown when trying to pass a value as an argument to a function that does not allow a range that includes the value. This can be encountered when: passing a value that is not one of the allowed string values to String.

## What is a ‘tyep error’?

In statistical hypothesis testing, a type I error is the mistaken rejection of the null hypothesis (also known as a "false positive" finding or conclusion; example: "an innocent person is convicted"), while a type II error is the mistaken acceptance of the null hypothesis (also known as a "false negative" finding ).

## What is a breakpoint?

 In software development, a breakpoint is an intentional stopping or pausing place in a program, put in place for debugging purposes.

## What does the word ‘debugger’ do in your code?


Definition: Debugging is the process of detecting and removing of existing and potential errors (also called as 'bugs') in a software code that can cause it to behave unexpectedly or crash. ... Description: To debug a program, user has to start with a problem, isolate the source code of the problem, and then fix it.