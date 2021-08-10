# React and Forms

---
## What is a ‘Controlled Component’?

A controlled component is a component that renders form elements and controls them by keeping the form data in the component's state. In a controlled component, the form element's data is handled by the React component (not DOM) and kept in the component's state.


**store the user's responses from the form into a state when they submit the form is better than update the state with their responses as soon as they enter them because we shouldn't have to type more lines of code, we can now pass the value to other UI elements too, or reset it from other event handlers.**

## How do we target what the user is entering if we have an event handler on an input field?


Since the value attribute is set on our form element, the displayed value will always be this. state. value, making the React state the source of truth. Since handle change runs on every keystroke to update the React state, the displayed value will update as the user types.

With a controlled component, the input’s value is always driven by the React state. While this means you have to type a bit more code, you can now pass the value to other UI elements too, or reset it from other event handlers.

**Example**
~~~
class FlavorForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: 'coconut'};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('Your favorite flavor is: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Pick your favorite flavor:
          <select value={this.state.value} onChange={this.handleChange}>
            <option value="grapefruit">Grapefruit</option>
            <option value="lime">Lime</option>
            <option value="coconut">Coconut</option>
            <option value="mango">Mango</option>
          </select>
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
~~~

___
[Try it on CodePen](https://codepen.io/gaearon/pen/JbbEzX?editors=0010)
___

## **The Conditional (Ternary) Operator Explained**

## Why would we use a ternary operator?

The JavaScript ternary operator is a useful tool that you'll encounter in code quite often. Ternary operators can make statements more concise and easy to reason about. If the syntax is new to you, the operator may seem a little confusing.

## Rewrite the following statement using a ternary statement:
~~~
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
  ~~~
**ternary statement**
~~~
x===y ? 'true':'false'
~~~
