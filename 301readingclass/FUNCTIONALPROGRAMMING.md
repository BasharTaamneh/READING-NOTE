# FUNCTIONAL PROGRAMMING


## What is functional programming?

Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data .

## What is a pure function and how do we know if something is a pure function?


the definition of a pure function is: The function always returns the same result if the same arguments are passed in. It does not depend on any state, or data, change during a program's execution. It must only depend on its input arguments.

## What are the benefits of a pure function?


One of the major benefits of using pure functions is they are immediately testable. They will always produce the same result if you pass in the same arguments. They also makes maintaining and refactoring code much easier.

👉 They’re easier to reason about

👉 They’re easier to combine

👉 They’re easier to test

👉They’re easier to debug

👉They’re easier to parallelize

FP developers talk about other benefits of writing pure functions. For instance, Venkat Subramaniam adds these benefits:

👉They are idempotent

👉They offer referential transparency

👉They are memoizable

👉They can be lazy


## What is immutability? 


he state or condition of being unchangeable:These findings contradict previous myths about the genetic immutability of intelligence at birth.

Immutable data structures are data structures that cannot be changed(mutated) after they are created. It is a powerful technique that allows us to make changes to our data structure without wiping state history. It also eliminates a whole class of nasty bugs(more on that later).

Let’s look at an example where we need to update and change the global state of our application. This example will show us the pitfalls of not using immutability. 


## What is Referential transparency?

Referential transparency and referential opacity are properties of parts of computer programs. An expression is called referentially transparent if it can be replaced with its corresponding value (and vice-versa) without changing the program's behavior.[1] This requires that the expression be pure, that is to say the expression value must be the same for the same inputs and its evaluation must have no side effects. An expression that is not referentially transparent is called referentially opaque.

In mathematics all function applications are referentially transparent, by the definition of what constitutes a mathematical function. However, this is not always the case in programming, where the terms procedure and method are used to avoid misleading connotations. In functional programming only referentially transparent functions are considered. Some programming languages provide means to guarantee referential transparency. Some functional programming languages enforce referential transparency for all functions.

The importance of referential transparency is that it allows the programmer and the compiler to reason about program behavior as a rewrite system. This can help in proving correctness, simplifying an algorithm, assisting in modifying code without breaking it, or optimizing code by means of memoization, common subexpression elimination, lazy evaluation, or parallelization.

~~~
~~~

## **Modules and require()**


## What is a module?

odule in Node. js is a simple or complex functionality organized in single or multiple JavaScript files which can be reused throughout the Node. ... Each module in Node. js has its own context, so it cannot interfere with other modules or pollute global scope. Also, each module can be placed in a separate .

## What does the word ‘require’ do?

the require() method is used to load and cache JavaScript modules. So, if you want to load a local, relative JavaScript module into a Node. js application, you can simply use the require() method.

## How do we bring another module into the file the we are working in?


👉 Creating and Exporting a module
Importing a Module

👉 Exporting multiple functions and values from a module

👉 Importing a module from a directory
Types of modules
