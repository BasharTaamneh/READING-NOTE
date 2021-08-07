#  Introduction to React and Components

## What is a component?


A component is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. It has an obviously defined interface and conforms to a recommended behavior common to all components within an architecture.

A software component can be defined as a unit of composition with a contractually specified interface and explicit context dependencies only. That is, a software component can be deployed independently and is subject to composition by third parties.

## What are the charactistics of a component?

1) **Reusability** − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

2) **Replaceable** − Components may be freely substituted with other similar components.

3) **Not context specific** − Components are designed to operate in different environments and contexts.

4) **Extensible** − A component can be extended from existing components to provide new behavior.

5) **Encapsulated** − A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

6) **Independent** − Components are designed to have minimal dependencies on other components.


## What are the advantages of using component based architecture?


1) **Reduced cost** − The use of third-party components allows you to spread the cost of development and maintenance.

2) **Ease of development** − Components implement well-known interfaces to provide defined functionality, allowing development without impacting other parts of the system.

3) **Reusable** − The use of reusable components means that they can be used to spread the development and maintenance cost across several applications or systems.

4) **Modification of technical complexity** − A component modifies the complexity through the use of a component container and its services.

5) **Reliability** − The overall system reliability increases since the reliability of each individual component enhances the reliability of the whole system via reuse.

6) **System maintenance and evolution** − Easy to change and update the implementation without affecting the rest of the system.

7) **Independent** − Independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development

---
~~~
~~~
---

## **Props and How to Use it in React?**

*React is a component-based library which divides the UI into little reusable pieces. In some cases, those components need to communicate (send data to each other) and the way to pass data between components is by using props.*

## What is props short for?

“Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.

But the important part here is that data with props are being passed in a uni-directional flow. (one way from parent to child).

Furthermore, props data is read-only, which means that data coming from the parent should not be changed by child components.


## How are props used in React?

- Firstly, define an attribute and its value(data).

- Then pass it to child component(s) by using Props.
- Finally, render the Props Data.


## What is the flow of props?


one-way data flow, which means the data has one, and only one way to be transferred to other parts of the application. In essence, this means child components are not able to update the data that is coming from the parent component. In React, data coming from a parent is called props.[1]

[1]geeksforgeeks.https://www.geeksforgeeks.org/unidirectional-data-flow/ 
