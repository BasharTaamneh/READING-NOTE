# thinking in React


## How would you break a mock into a component hierarchy?

**Step 1:** Break The UI Into A Component Hierarchy.

**Step 2:** Build A Static Version in React.

**Step 3:** Identify The Minimal (but complete) Representation Of UI State.

**Step 4:** Identify Where Your State Should Live.


## What is the single responsibility principle and how does it apply to components?

 In React, the Single Responsibility Principle means that a component is required to have only one reason to change. In short, the Single Responsibility Principle means that code with the same functionality should not exist in multiple places. Component Composition makes SRP easier to maintain so that there can be a single source of truth.

Single responsibility principle describes how to split requirements into components, encapsulation describes how to organize these components, and composition describes how to glue the whole system back.

## What does it mean to build a ‘static’ version of your application?

To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state, don’t use state at all to build this static version. State is reserved only for interactivity, that is, data that changes over time. Since this is a static version of the app, you don’t need it.

You can build top-down or bottom-up. That is, you can either start with building the components higher up in the hierarchy (i.e. starting with FilterableProductTable) or with the ones lower in it (ProductRow). In simpler examples, it’s usually easier to go top-down, and on larger projects, it’s easier to go bottom-up and write tests as you build.

At the end of this step, you’ll have a library of reusable components that render your data model. The components will only have render() methods since this is a static version of your app. The component at the top of the hierarchy (FilterableProductTable) will take your data model as a prop. If you make a change to your underlying data model and call ReactDOM.render() again, the UI will be updated. You can see how your UI is updated and where to make changes. React’s one-way data flow (also called one-way binding) keeps everything modular and fast.


## Once you have a static application, what do you need to add?

 The Minimal (but complete) Representation Of UI State.

 ## What are the three questions you can ask to determine if something is state?


 1. Is it passed in from a parent via props? If so, it probably isn’t state.

2. Does it remain unchanged over time? If so, it probably isn’t state.

3. Can you compute it based on any other state or props in your component? If so, it isn’t state.


## How can you identify where state needs to live?




Remember: React is all about one-way data flow down the component hierarchy. It may not be immediately clear which component should own what state. This is often the most challenging part for newcomers to understand, so follow these steps to figure it out:


For each piece of state in your application:

1) Identify every component that renders something based on that state.

2)  Find a common owner component (a single component above all the components that need the state in the hierarchy).


3) Either the common owner or another component higher up in the hierarchy should own the state.
   
4) If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.



