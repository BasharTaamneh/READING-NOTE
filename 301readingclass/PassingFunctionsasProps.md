# Passing Functions as Props

## What does .map() return?
map() function returns a map object(which is an iterator) of the results after applying the given function to each item of a given iterable (list, tuple etc..)

## to loop through an array and display each value in JSX, look to this example

~~~
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li>{number}</li>
  );
  return (
    <ul>{listItems}</ul>
  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,
  document.getElementById('root')
);
~~~
When you run this code, you’ll be given a warning that a key should be provided for list items. A “key” is a special string attribute you need to include when creating lists of elements. We’ll discuss why it’s important in the next section.

___
Let’s assign a key to our list items inside numbers.map() and fix the missing key issue.
~~~
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>
      {number}
    </li>
  );
  return (
    <ul>{listItems}</ul>
  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,
  document.getElementById('root')
);
~~~



The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys.

When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort.

We don’t recommend using indexes for keys if the order of items may change. This can negatively impact performance and may cause issues with component state. Check out Robin Pokorny’s article for an in-depth explanation on the negative impacts of using an index as a key. If you choose not to assign an explicit key to list items then React will default to using indexes as keys.

**Each list item needs a unique key**

## What is the purpose of a key?

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.


~~~
~~~
___

## **The Spread Operator**

## What is the spread operator?


The spread operator is a new addition to the set of operators in JavaScript ES6. It takes in an iterable (e.g an array) and expands it into individual elements. The spread operator is commonly used to make shallow copies of JS objects. Using this operator makes the code concise and enhances its readability.

---

**spread operator is useful for many different routine tasks in JavaScript, including some of the following:**

1) Adding to state in React
1) Using an array as arguments.
1) Concatenating or combining arrays.
1) Copying an array.


## Examples of using (…) => The Spread Operator

~~~
[...["😋😛😜🤪😝"]] // Array [ "😋😛😜🤪😝" ]
[..."🙂🙃😉😊😇🥰😍🤩!"] // Array(9) [ "🙂", "🙃", "😉", "😊", "😇", "🥰", "😍", "🤩", "!" ]

const hello = {hello: "😋😛😜🤪😝"}
const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}

const helloWorld = {...hello,...world}
console.log(helloWorld) // Object { hello: "😋😛😜🤪😝", world: "🙂🙃😉😊😇🥰😍🤩!" }
~~~

## Copying an array
Using the … spread operator 
~~~
const fruits = ['🍏','🍊','🍌','🍉','🍍']
const moreFruits = [...fruits];
console.log(moreFruits) // Array(5) [ "🍏", "🍊", "🍌", "🍉", "🍍" ]
fruits[0] = '🍑'
console.log(...[...fruits,'...',...moreFruits]) //  🍑 🍊 🍌 🍉 🍍 ... 🍏 🍊 🍌 🍉 🍍
~~~

## Copying an array
Using the … spread operator
~~~
const fruits = ['🍏','🍊','🍌','🍉','🍍']
const moreFruits = [...fruits];
console.log(moreFruits) // Array(5) [ "🍏", "🍊", "🍌", "🍉", "🍍" ]
fruits[0] = '🍑'
console.log(...[...fruits,'...',...moreFruits]) //  🍑 🍊 🍌 🍉 🍍 ... 🍏 🍊 🍌 🍉 🍍
~~~

## How to Pass Functions Between Components

**see this video [link](https://youtu.be/c05OL7XbwXU) first**

 the first step that the developer does to pass functions between components? create a function to change the state wherever it is.

 *the increment function does increasing the count value of the people array*

 ## How to execute child component function from the parent component?

 
In order to execute a function from a child component, you will need to use Refs. React supports a special attribute that you can attach to any component, that's the ref attribute, it takes a callback function, and you can access the functions of the child component in the parent accessing this.refs.REF_NAME.METHOD_NAME.

We are going to create a Parent element, it will render a \<Child/> component. As you can see, the component that will be rendered, you need to add the ref attribute and provide a name for it. Then, the triggerChildAlert function, located in the parent class will access the refs property of the this context (when the triggerChildAlert function is triggered will access the child reference and it will has all the functions of the child element).


~~~
class Parent extends React.Component {
    triggerChildAlert(){
        this.refs.child.showAlert();
    }

    render() {
        return (
            <div>
                {/* Note that you need to give a value to the ref parameter, in this case child*/}
                <Child ref="child" />
                <button onClick={this.triggerChildAlert}>Click</button>
            </div>
        );
    }
}
~~~
Now, the child component, as theoretically designed previously, will look like:

~~~

class Child extends React.Component {
    showAlert() {
        alert('Hello World');
    }

    render() {
        return (
            <h1>Hello</h1>
        );
    }
}
~~~

The showAlert method is the only method that will be accesible in this.refs.child in the parent component.


