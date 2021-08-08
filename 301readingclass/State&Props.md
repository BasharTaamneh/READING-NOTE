# State and Props

![](https://miro.medium.com/max/2000/0*0saPKFiTUk6W3FYp)

**React render() is being called before componentDidMount()**

*hen a component is mounted it is being inserted into the DOM. This is when a constructor is called.componentWillMount is pretty much synonymous with a constructor and is invoked around the same time. componentDidMount will only be called once after the first render.*


## What is the very first thing to happen in the lifecycle of React?

static getDerivedStateFromProps() The static getDerivedStateFromProps is the first React lifecycle method to be invoked during the updating phase.

##  in the order that they happen!
1) constructor
1) componentWillUnmount
1) render
1)  React Updates
1) componentDidMount

## What does componentDidMount do?
The componentDidMount() method allows us to execute the React code when the component is already placed in the DOM (Document Object Model). This method is called during the Mounting phase of the React Life-cycle i.e after the component is rendered.


## What types of things can you pass in the props? 
Props (aka "properties") in React allows us to pass values from a parent component down to a child component.

The values can be any data type, from strings to functions, objects, etc..

## What is the big difference between props and state?

The key difference between props and state is that state is internal and controlled by the component itself while props are external and controlled by whatever renders the component.

![](https://i.ytimg.com/vi/aLmwln09Tbs/mqdefault.jpg)


## When do we re-render our application?

React components automatically re-render whenever there is a change in their state or props. A simple update of the state, from anywhere in the code, causes all the User Interface 

## What are some examples of things that we could store in state?


 The important thing to know about local state is that when a state value changes, it triggers a re-render.

This state can be passed down to children as props, which allows you to separate your components between smart data-components and dumb presentational-components if you chose.

