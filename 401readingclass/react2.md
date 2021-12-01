# React Context for Beginners

## What is React context?

* React context allows us to pass down and use (consume) data in whatever component we need in our React app without using props.

In other words, React context allows us to share data (state) across our components more easily.

## When should you use React context?
React context is great when you are passing data that can be used in any component in your application.

These types of data include:

> Theme data (like dark or light mode)

> User data (the currently authenticated user)

> Location-specific data (like user language or locale)

Data should be placed on React context that does not need to be updated often.

Why? Because context was not made as an entire state management system. It was made to make consuming data easier.

You can think of React context as the equivalent of global variables for our React components.


## What problems does React context solve?

React context helps us avoid the problem of props drilling.

Props drilling is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.

Here is an example of props drilling. In this application, we have access to theme data that we want to pass as a prop to all of our app's components.

As you can see, however, the direct children of App, such as Header, also have to pass the theme data down using props.

```javascript
export default function App({ theme }) {
  return (
    <>
      <Header theme={theme} />
      <Main theme={theme} />
      <Sidebar theme={theme} />
      <Footer theme={theme} />
    </>
  );
}

function Header({ theme }) {
  return (
    <>
      <User theme={theme} />
      <Login theme={theme} />
      <Menu theme={theme} />
    </>
  );
}
```

What is the issue with this example?

The issue is that we are drilling the theme prop through multiple components that don't immediately need it.

The Header component doesn't need theme other than to pass it down to its child component. In other words, it would be better for User , Login and Menu to consume the theme data directly.

This is the benefit of React context – we can bypass using props entirely and therefore avoid the issue of props drilling.

## How do I use React context?
Context is an API that is built into React, starting from React version 16.

This means that we can create and use context directly by importing React in any React project.

**There are four steps to using React context:**

> Create context using the createContext method.

> Take your created context and wrap the context provider around your component tree.

> Put any value you like on your context provider using the value prop.

> Read that value within any component by using the context consumer.

Does all this sound confusing? It's simpler than you think.

Let's take a look at a very basic example. In our App, let's pass down our own name using Context and read it in a nested component: User

```javascript
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  return (
    <UserContext.Consumer>
      {value => <h1>{value}</h1>} 
      {/* prints: Reed */}
    </UserContext.Consumer>
  )
}
```


## Let's break down what we are doing, step-by-step:

> Above our App component, we are creating context with React.createContext() and putting the result in a variable, UserContext. In almost every case, you will want to export it as we are doing here because your component will be in another file. Note that we can pass an initial value to our value prop when we call React.createContext().

> In our App component, we are using UserContext. Specifically UserContext.Provider. The created context is an object with two properties: Provider and Consumer, both of which are components. To pass our value down to every component in our App, we wrap our Provider component around it (in this case, User).

> On UserContext.Provider, we put the value that we want to pass down our entire component tree. We set that equal to the value prop to do so. In this case, it is our name (here, Reed).

> In User, or wherever we want to consume (or use) what was provided on our context, we use the consumer component: UserContext.Consumer. To use our passed down value, we use what is called the render props pattern. It is just a function that the consumer component gives us as a prop. And in the return of that function, we can return and use value.

## What is the useContext hook?
Looking at the example above, the render props pattern for consuming context may look a bit strange to you.

Another way of consuming context became available in React 16.8 with the arrival of React hooks. We can now consume context with the useContext hook.

Instead of using render props, we can pass the entire context object to React.useContext() to consume context at the top of our component.
