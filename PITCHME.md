---?color=black
@title[Title]

@snap[west headline text-white span-100]
3D Slicer: DBS Guide<br>

@size[40%](Lab Retreat 2019<br>June 22, 2019)
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](greydon.gilmore@gmail.com)
@snapend


---
@title[Contents]
### Contents

@ol[](false)
- what is DBS Guide?
- why 3D Slicer?
- methods
- case example
@olend


---
@title[What is React.js?]
### What is React.js?

@ul[list-bullets-black](true)
- It's a library for building @size[1.5em](user interfaces)
- React builds the UI with @size[1.5em](components)
- These components usually have changing @size[1.5em](data)
- React was created at Facebook
- It's used by Netflix, NY Times, Uber, Twitter, etc.
- Visit React.js [website](https://reactjs.org/)

@ulend


---
@title[Why React.js?]
### Why React.js?

@ul[list-bullets-black](true)
- React is becoming very popular [*](https://insights.stackoverflow.com/survey/2018/)
- It uses a Component based architecture [*](https://twitter.com/lyit)
- React builds website UI using @size[1.5em](components)
- @size[1.5em](Components)
- @size[1.75em](Components)
- @size[2.0em](Components)
@ulend


---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- **Setup**
- Your First Component
@olend


---
@title[React Setup]
### React.js Setup

We are going to need:
@ul[list-bullets-black](true)
- the _React Developer Tools_ browser extension
- the _Create React App_ tool 

@ulend


---
@title[React Setup]
### React Developer Tools

@ul[list-bullets-black](true)
- Install from [Chrome Webstore](https://chrome.google.com/webstore/category/extensions)
- Search for *React Developer Tools*
- It helps you:
  - identify any website you visit that uses React [*](https://www.instagram.com/?hl=en)
  - provides a React tab in the console
- Install it now!
@ulend

---
@title[React Setup]
### Create React App

@ul[list-bullets-black](true)
- Create React App creates a new React app for you
- You'll need `node` version 8 || > to install it
- Let's install it now...
@ulend

---
@title[React Setup]
### Create React App

Install Create React App

```
C:\> node -v
v8.9.4

C:\> npm install -g create-react-app
     ...

C:\>
```
@ul[list-bullets-black](true)
- Where was it installed?
- `c:\users\YOU\AppData\Roaming\npm`
- add folder to `PATH`...
@ulend

---
@title[React Setup]
### Create React App

Setup `PATH`
```
C:\> set PATH=%PATH%;c:\users\YOU\AppData\Roaming\npm

```
Test it works:
```
C:\> create-react-app
     ...
```
@ul[list-bullets-black](true)
- Let's create our first React.js app...
@ulend

---
@title[Hello React App]
### Hello React App

```
C:\> create-react-app helloreact
     ...
```
@ul[list-bullets-black](true)
- Let's run the app...
@ulend

---
@title[Hello React App]
### Hello React App

```
C:\> cd helloreact
C:\helloreact> npm start
               ...

```
@ul[list-bullets-black](true)
- Use Chrome to visit [http://localhost:3000](http://localhost:3000)
- Open the app with VS Code for a quick tour...
@ulend

---
@title[Hello React Quick Tour]
### Hello React Quick Tour

@ul[list-bullets-black](true)
- `public/index.html`
  - the `<div>`
- `src/index.js`
  - imports
  - `ReactDOM.render()`
- `src/App.js`
  - imports
  - `App` component
  - render JSX
- View the `<App>` component in React tab
@ulend

---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- Setup
- **Your First Component**
@olend


---
@title[React Components]
### React Components

@ul[list-bullets-black](true)
- React is popular because of its @size[1.5em](component based structure)
- We create a UI by using a collection of components
- We create components using the class [React.Component](https://reactjs.org/docs/react-component.html)
- Let's create our @size[1.5em](React Component)...
@ulend


---
@title[Your First Component]
### Your First Component

```javascript
// src/HelloWorld.js
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  render() {
    return (
      <h1>Hello World!</h1>
    );
  }
}
export default HelloWorld;
```
@[2](import React library)
@[2,3](import ReactDOM to render the component)
@[2,3,5,11](Our component extends from a React.Component)
@[2,3,5,11,6,10](All components MUST have a render() method)
@[2,3,5,11,6,10,7,8,9](return the component element)
@[8](this is JSX)
@[12](export the component class)
@[*]()

@ul[list-bullets-black](true)
- Let's render this component to our HTML page...
@ulend

---
@title[Your First Component]
### Your First Component

```html
<!-- public/index.html -->
<!doctype html>
<html lang="en">
<head>
  <title>React App</title>
</head>
<body>
  <div id="root"></div>
</body>
</html>
```

@[8](We'll add the component here)
@[*]()

---
@title[Your First Component]
### Your First Component

```javascript
// src/index.js
import React from 'react';
import ReactDOM from 'react-dom';
import HelloWorld from './HelloWorld.js';

ReactDOM.render(<HelloWorld />, 
                document.getElementById('root'));
```

@[2,3](import React and ReactDOM)
@[2,3,4](import our new component)
@[2,3,4,6-7](render our HelloWorld component in the div)
@[*]()

@ul[list-bullets-black](true)
- View in browser 
- and examine the React console tab too
@ulend


---
@title[Exercise]
### React.js Exercise 1 – Getting Started

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx1.md)


---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- Setup
- Your First Component
- **JSX**
@olend



---
@title[What is JSX?]
### What is JSX?

This is JSX

```javascript
const element = <h1>Hello, world!</h1>;
```

@ul[](true)
- It's a syntax extension to JavaScript
- React recommends using it to render UI components with elements
- Let's see why you use it...
@ulend

---
@title[JSX]
### JSX
Previously our first React Component looked like this:

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  render() {
    return (
      <h1>Hello World!</h1>
    );
  }
}
export default HelloWorld;
```
@[7](JSX creates the `<h1>` element)
@[*]()

@ul[](true)
- Without JSX we'd have to do this...
@ulend


---
@title[JSX]
### JSX
We'd need to use the [React.createElement()](https://reactjs.org/docs/react-api.html#createelement) function

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  render() {
    return React.createElement('<h1>',null,'Hello World!');
  }
}
export default HelloWorld;
```
@[6](using createElement() for the `<h1>` element)
@[*]()

@ul[](true)
- Code written with JSX is converted to use `React.createElement()` anyway
- It would be worse for less simple components..
@ulend


---
@title[JSX]

A not so complex component using JSX

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  render() {
    return(
      <div id="myDiv">
        <h1>Hello World!</h1>
      </div>
    );   
  }
}
export default HelloWorld;
```
@[7-10](JSX)
@[*]()


---
@title[JSX]

Same component using `React.createElement()`

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  render() {
    return React.createElement(
                 '<div>', 
                 {id: 'myDiv'}, 
                 React.createElement('h1',
                                      null,
                                      'Hello World!'));
    );
  }
}
export default HelloWorld;
```
@[6-11](!JSX)
@[*]()
@ul[](true)
- You can see why using JSX is better
@ulend

---
@title[JSX Expressions]
### JSX Expressions

<!-- With JSX we can use expressions too -->

```javascript
import React from 'react';
import ReactDOM from 'react-dom'
const name='Bob';

class HelloWorld extends React.Component {
  render() {
    return(
      <div id="myDiv">
        <h1>Hello {name}</h1>
      </div>
    );   
  }
}
export default HelloWorld;
```
@[3](name is Bob)
@[3,5-13](will print Hello Bob)
@[*]()


@ul[](true)
- Expressions can be code that resolves to any value e.g...
@ulend

---
@title[JSX Expressions]
### JSX Expressions

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  render() {
    return(
      <div id="myDiv">
        <h1>1+2={1+2}</h1>
      </div> 
    );   
  }
}
export default HelloWorld;
```
@[7-9]()
@[*]()

@ul[](true)
- Another example with a function...
@ulend

---
@title[JSX Expressions]
### JSX Expressions

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
  add = (num1,num2) => {return num1+num2;}

  render() {
    return(
      <div id="myDiv">
        <h1>1+2={add(1,2)}</h1>
      </div>
    );   
  }
}
export default HelloWorld;
```
@[4,5,14]()
@[4,5,14,9-11]()
@[*]()


---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- Setup
- Your First Component
- JSX
- **Component Properties (Props)**
@olend

---
@title[Component Properties]
### Component Properties

@ul[list-bullets-black](true)
- The previous component `HelloWorld` displayed static content
- To display a dynamic content use React @size[1.5em](Props)...
@ulend


---
@title[Component Properties]
### Component Properties

Component properties (props) are accessible with `this.props` object

```javascript
class HelloWorld extends React.Component {
  render() {
    return (
      <h1>Hello {this.props.name}</h1>
    );
  }
}
export default HelloWorld;
...
ReactDOM.render(<HelloWorld name="Bob"/>,document.getElementById('root'));
```
@[10](pass a name property like this)
@[10,4](access it with component like this)
@[*]()

@ul[list-bullets-black](true)
- Pass multiple properties like this...
@ulend


---
@title[Component Properties]
### Component Properties

```javascript
class HelloWorld extends React.Component {
  render() {
    return (
     <h1>{this.props.name} CU in {this.props.mins} mins</h1>
    );
  }
}
export default HelloWorld;
...
ReactDOM.render(<HelloWorld name="Bob" mins={5} />,document.getElementById('root'));
```
@[10](use expression syntax {} for non-string properties)
@[10,4](access it within a component like this)
@[*]()

---
@title[React Function Components]
### React Function Components

@ul[list-bullets-black](false)
- We've seen how to create a component with a @size[1.5em](class)
- We can also create a component with a @size[1.5em](function)
- For example...
@ulend

---
@title[Component Properties]
### Component Properties

```javascript
import React from 'react';
import ReactDOM from 'react-dom'

const HelloWorld = function(props) {
  return(
    <div>
     <h1>{props.name} CU in {props.mins} mins</h1>
    </div>
  )
}
export default HelloWorld;
...
ReactDOM.render(<HelloWorld name="Bob" mins={5} />,document.getElementById('root'));
```
@[4,10](function declaration)
@[*](everthing else is the same)

---
@title[Class Components v Function Components]
### Class v Function Components

@ul[list-bullets-black](true)
- You may see component functions elsewhere
- But I'll use component classes instead, because...
  - a class component has @size[1.5em](state)
  - a class component has @size[1.5em](lifecycle hooks)
- We'll explain this next
@ulend


---
@title[Exercise]
### React.js Exercise 2 – React Props

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx2.md)





---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- Setup
- Your First Component
- JSX
- Component Properties 
- **State**
@olend




---
@title[State]
### State

@ul[](true)
- Component @size[1.5em](state) is a key concept in React
- State is simply the @size[1.5em](object data) associated with a component
- Specifically, state is data a component has that when changed affects how the component looks and behaves
- Your components @size[1.5em](react) to changes in state
- An example...
@ullist

---
@title[State]
### State

![](lectures/React/images/MyButton.png)

@ul[](true)
- Let's create a simple button component
- It's caption will be part of its state
@ullist



---
@title[State]
### State

```javascript
import React from 'react';

class MyButton extends React.Component {
    constructor() {
      super();
      this.state = { caption: "hello" };
    }  
    render() {
      return (
        <button>{this.state.caption}</button>
      );
    }
}
export default MyButton;
```
@[3,13](MyButton component)
@[3,13,4,7](Has a constructor)
@[3,13,4,7,5](Always call super())
@[3,13,4,7,5,6](Create Component State using this.state object)
@[*](Render the button using this.state.caption)

@ul[](true)
- ``MyButton`` component has state...
@ulend


---
@title[State]
<!-- ### State -->

![](lectures/React/images/MyButton2.png)


@ul[](true)
- Changing the state ``caption`` has this effect...
@ulend

---
@title[State]
<!-- ### State -->

![](lectures/React/images/MyButton3.png)


@ul[](true)
- Changing the state caption changed how the button looked
@ulend


---
@title[State]
### State

@ul[](true)
- Changing state changes how the components look
- This is a key concept of React
- This is a powerful concept happening here
- Component look and behaviour is driven by it's state
- It's a data (state) driven component model
- Time for a better example...
@ulend

---
@title[State]
### State

![](lectures/React/images/Clock1.png)

@ul[](false)
- Let's create a live Clock component...

@ullist

---
@title[State]
### Clock (Good old days)

```html
<div>It is <span id='time'></span></div>

<script>
function tick() {
  document.getElementById('time').innerHTML=
                          new Date().toLocaleTimeString();
}
setInterval(tick, 1000);
</script>
```
@ul[](true)
- Our new Clock component will have its own timer and update itself every second
- We'll make a Clock component truly **reusable** and **encapsulated**
@ullist



---
@title[Clock]
### Clock Component

Clock Component class

```javascript
import React from 'react';

export default class Clock extends React.Component {

}
```

---
@title[Clock]
### Clock Component

Constructor with State

```javascript
import React from 'react';

export default class Clock extends React.Component {
  constructor() {
    super();
    this.state = {date: new Date()};
  }

}
```
@[4-7]()
@[*]()

@ul[](false)
- Always uses ``this.state`` object for state
@ullist

---
@title[Clock]
<!-- ### Clock Component -->

Render it

```javascript
import React from 'react';

export default class Clock extends React.Component {
  constructor() {
    super();
    this.state = {date: new Date()};
  }
  render() {
    return (
      <div>{this.state.date.toLocaleTimeString()}</div>
    );
  }
}
```
@[8-12]()
@[*]()

@ul[](true)
- So far this will display static time
- Let's update the time every second...
@ullist


---
@title[Clock]
<!-- ### Clock Component -->

Update time

```javascript
export default class Clock extends React.Component {
  constructor() {
    super();
    this.state = {date: new Date()};
    setInterval(this.tick,1000);
  }
  tick() {
    this.setState( { date: new Date() });
  }
  render() {
    return (
      <div>{this.state.date.toLocaleTimeString()}</div>
    );
  }
}
```
@[2-6]()
@[5]()
@[5,7-9](calls tick() every second)
@[*]()

@ul[](true)
- Almost done, but we get this error...
@ullist

---
@title[State]
<!-- ### State -->

![](lectures/React/images/Clock2.png)

@ul[](true)
- `this` is not a reference to the class anymore
- `this` is a reference to the `setInterval()` function
- Two possible solutions...
@ullist

---
@title[State]
### this is the end?

Choose from these 2 solutions:

@ol[](true)
- Bind `this` to `tick()` as a reference to the class
- Use an arrow function for `tick()`
@ullist

---
@title[Clock]
<!-- ### Clock Component -->


Bind `this` to `tick()` 


```javascript
export default class Clock extends React.Component {
  constructor() {
    super();
    this.state = {date: new Date()};
    this.tick = this.tick.bind(this);
    setInterval(this.tick,1000);
  }
  tick() {
    this.setState( { date: new Date() });
  }
  render() {
    return (
      <div>{this.state.date.toLocaleTimeString()}</div>
    );
  }
}
```
@[2-7]()
@[5](the method tick is binded to the class this keyword)
@[*]()

---
@title[Clock]
<!-- ### Clock Component -->

Arrow function ``tick()`` 

```javascript
export default class Clock extends React.Component {
  constructor() {
    super();
    this.state = {date: new Date()};
    setInterval(this.tick,1000);
  }
  //tick() {
  tick = () => {
    this.setState( { date: new Date() });
  }
  render() {
    return (
      <div>{this.state.date.toLocaleTimeString()}</div>
    );
  }
}
```
@[7-10]()
@[*]()

---
@title[Clock]
### Clock Component

Finally, we get to render the Clock component

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import Clock from './Clock.js';

ReactDOM.render(<Clock />, document.getElementById('root'));
```
@[3]()
@[3,5]()
@[*]()


---
@title[Exercise]
### React.js Exercise 3 – React State

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx3.md)


---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- Setup
- Your First Component
- JSX
- Component Properties 
- State
- **Event Handling**

@olend

---
@title[Handling Events]
### Handling Events

Let's add a `onclick` event to `<MyButton>`...


---
@title[Handling Events]
<!-- ### Handling Events -->

```javascript
class MyButton extends React.Component {
  constructor() {
    super();
    this.state = { caption: "hello" };
  }  
  change = () => {
    this.setState ( { caption: "hi" } );
  }
  render() {
    return (
      <button onClick={this.change}>
        {this.state.caption}
      </button>
    );
  }
}
export default MyButton;
```
@[11-13](onClick event calls change method)
@[11-13,6,7,8](set the caption to hi)
@[*]()

---
@title[Exercise]
### React.js Exercise 4 – React Event Handling - Part 1-3

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx4.md)



---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- Setup
- Your First Component
- JSX
- Component Properties 
- State
- Event Handling
- **Component Lifecycle**
@olend



---
@title[Component Lifecycle]
### Component Lifecycle

@ul[](true)
- React Components have a lifecycle 
- Specifically when a component is:
  - @size[1.5em](mounting) - added to the DOM
  - @size[1.5em](updating) - updated 
  - @size[1.5em](unmounting) - removed from the DOM 
- When a component lifecycle changes specific methods are called...
@ulend


---
@title[Component Lifecycle]
### Component Lifecycle

![](lectures/React/images/lifeCycle.png)

@[](#1 constructor() - good for initialising state, etc. )
@[](#2 render() )
@[](#3 componentDidMount() )
@[](#4 render()    (if necessary))
@[](#5 componentDidUpdate()  )
@[](#6 componentWillUnmount() )

@ul[](true)
- We'll use those highlighted in green...
@ulend


---
@title[Component Lifecycle]
### Component Lifecycle

@ul[](true)
- `componentDidMount()` is called after the DOM renders the component for the first time
- `componentDidUpdate()` is called after DOM re-renders component
- `componentWillUnmount()` is called after DOM removes the component
- Let's see these methods used with a `<Timer>`...
@ulend

---
@title[Component Lifecycle]
### Component Lifecycle

@ul[](false)
- The timer will start at 10 seconds
@ulend

```javascript
ReactDOM.render(<Timer value={10} />, 
                document.getElementById('root'));
```


---

```javascript
import React from 'react';

class Timer extends React.Component {
  constructor(props) {
    super(props);
    this.state = { time: this.props.value };
  }
  render() {
    return (
      <div>
        {this.state.time}
      </div>
    );
  }
  ...
}
export default Timer;
```
@[1,3,16](Timer component)
@[4-7](Constructor uses prop to initialise time value)
@[4-7,8-14](Render the time)
@[*]()

@ul[](true)
- Use `componentDidMount()` to start the timer...
@ulend

---

```javascript
class Timer extends React.Component {
  constructor(props) {
    super(props);
    this.state = { time: this.props.value };
  }
  ...
  componentDidMount() {
    this.timerID = setInterval(this.tick,1000);
  }
}
```
@[7-9](componentDidMount() is a great place to start the timer)
@[7-9](we get a reference to the timer too)
@[*]()

@ul[](true)
- Add `tick()` method...
@ulend

---

```javascript
class Timer extends React.Component {
  constructor(props) {
    super(props);
    this.state = { time: this.props.value };
  }
  ...
  componentDidMount() {
    this.timerID = setInterval(this.tick,1000);
  }
  tick = () => {
    if(this.state.time==0)
      return;
    this.setState( { time: this.state.time-1 } );
  }
}
```
@[10,14](tick as arrow function)
@[10,14](no need to bind this to tick)
@[10,14,11-12](if time is ZERO return)
@[10,14,11-12,13](decrement time)
@[*]()

@ul[](true)
- Finally use `componentWillUnmount()` method to cleanup...
@ulend


---
```javascript
class Timer extends React.Component {
  ...
  componentDidMount() {
    this.timerID = setInterval(this.tick,1000);
  }
  tick = () => {
    if(this.state.time==0)
      return;
    this.setState( { time: this.state.time-1 } );
  }
  componentWillUnmount() {
    clearInterval(this.timerID);
  }
}
```
@[4,11-13](clear the timer using reference we got earlier)
@[*]()

@ul[](true)
- That's it.
@ulend

---
@title[Component Lifecycle]
### Component Lifecycle

@ul[](true)
- In `<Timer>` we used the `componentDidMount()` lifecycle method to start the timer
- In `<Timer>` we used the `componentWillUnmount()` lifecycle method to stop the timer
- Later we'll use `componentDidMount()` to @size[1.5em](fetch data)
@ulend

---
@title[Exercise]
### React.js Exercise 4 - Part 4

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx4.md)

---
@title[Contents]
### Contents

@ol[](false)
- ...
- State
- Event Handling
- Component Lifecycle
- **Conditional Rendering**
@olend


---
@title[Conditional Rendering]
### Conditional Rendering

@ul[]()
- We understand an `if` statement like this
@ulend

```javascript
var on = true;
if(on)
  return 'on';
else
  return 'off';
```

@ul[](true)
- JavaScript has a shortcut notation for this too
- It's called a @size[1.5em](ternary) operator...
@ulend

---
@title[Conditional Rendering]
### Conditional Rendering

@ul[]()
- A ternary operator version
@ulend

```javascript
var on = true;
on ? 'on' : 'off';
```

@ul[](true)
- The ternary operator takes three operands
  - the condition
  - the expression if true
  - the expression if false
- We can use them in React for _conditional rendering_...
@ulend



---
@title[Conditional Rendering]
### Conditional Rendering

Let's create a `<Switch>` component to toggle on/off

![](/lectures/React/images/SwitchOff.png)
<!-- ![](images/SwitchOff.png) -->

![](/lectures/React/images/SwitchOn.png)
<!-- ![](images/SwitchOn.png) -->

---

Basic component code:
```javascript
import React from 'react';

class Switch extends React.Component {
  constructor() {
    super();
  }
  render() {
    return (
      <div>
        <button>Toggle</button>
        <p>The switch is ???</p>
      </div>
    );
  }
}
export default Switch;
```
@ul()[true]
- Let's add state for on/off...
@ulend

---

```javascript
class Switch extends React.Component {
  constructor() {
    super();
    this.state = { on: false };
  }
  render() {
    return (
      <div>
        <button>Toggle</button>
        <p>The switch is ???</p>
      </div>
    );
  }
}
export default Switch;
```
@[4](on state)
@[*]()
@ul()[true]
- Add event handler for button...
@ulend

---

```javascript
class Switch extends React.Component {
  constructor() {
    super();
    this.state = { on: false };
  }
  render() {
    return (
      <div>
        <button onClick={this.toggle}>Toggle</button>
        <p>The switch is ???</p>
      </div>
    );
  }
  toggle = () => {
    this.setState( { on: !this.state.on } );
  }
}
export default Switch;
```
@ul()[true]
- And finally the conditional rendering...
@ulend


---
```javascript
import React from 'react';

class Switch extends React.Component {
  constructor() {
    super();
    this.state = { on: false };
  }
  render() {
    return (
      <div>
        <button onClick={this.toggle}>Toggle</button>
        <p>The switch is {this.state.on ? 'on' : 'off'}</p>
      </div>
    );
  }
  toggle = () => {
    this.setState( { on: !this.state.on } );
  }
}
export default Switch;
```

---
@title[Contents]
### Contents

@ol[](false)
- ...
- State
- Event Handling
- Component Lifecycle
- Conditional Rendering
- **Previous State**
@olend

---
@title[Previous State]
### Previous State

```javascript
toggle = () => {
    this.setState( { on: !this.state.on } );
  }
```
- In the `<Switch>` component the previous state of `on` was needed to set the new state
- There is a potential problem here because

> `setState()` does not always immediately update the component state!

- It is recommended we do this...

---
@title[Previous State]
### Previous State

Instead of this:
```javascript
toggle = () => {
  this.setState( { on: !this.state.on } );
}
```

Do this:
```javascript
toggle = () => {
  this.setState(prevState => (
    { on: !prevState.on }
  ));
}
``` 

---
@title[Exercise]
### React.js Exercise 4 – Part 5

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx4.md)


---
@title[Contents]
### Contents

@ol[](false)
- ...
- State
- Event Handling
- Component Lifecycle
- Conditional Rendering
- Previous State
- **Fetching Data**
@olend

---
@title[Fetching Data]
### Fetching Data

Let's see a component `<Clubs>` that uses static data...

---

```javascript
class Clubs extends React.Component {
  constructor() {
    super();
    this.state = { "clubs": [
        {"name": "Manchester United", "stadium": "Old Trafford"},
        {"name": "Liverpool", "stadium": "Anfield"},
        {"name": "Arsenal", "stadium": "Emirates"},
        {"name": "Manchester City", "stadium": "Ethidad"}]
    };
  }
  render() {
    return (
      <div><h2>Clubs</h2>
      {this.state.clubs.map((item) => {
                              return <p>{item.name}</p>; })}
      </div>
    );
  }
}
```
@[1,20](Clubs class component)
@[1,20,2-10](state data)
@[1,20,2-10,11-18](render state data)

---

![](lectures/React/images/Clubs.png)

---
@title[Fetching Data]
### Fetching Data

@ul[](true)
- A better way is to fetch the data using the `fetch()` method
- `fetch()` is very similar to an Ajax request
- Use it to fetch data from any valid URL source, e.g.
  - a PHP program
  - REST API request
- We'll use an Express File Server to get data...
@ulend


---
@title[Fetching Data]
### Simple File Server

```javascript
// fileServer/index.js
var express = require("express");
var cors = require("cors");

var app = express();

app.use(cors());
app.use(express.static('public'));

var myServer = app.listen(5000, function() {
  console.log("File Server listening on port 5000");
});
```
Data is stored in a file `clubs.json`...

---
@title[Fetching Data]

```javascript
// fileServer/public/clubs.json
{  
  "clubs":[  
    {"name":"Manchester United","stadium":"Old Trafford"},
    {"name":"Liverpool","stadium":"Anfield"},
    {"name":"Arsenal","stadium":"Emirates"},
    {"name":"Manchester City","stadium":"Ethidad"}
  ]
}
```
Let's see how to fetch this data...

---

![](lectures/React/images/Clubs_json.png)

Let's use this in a new component...

---

```javascript
class ClubsV2 extends React.Component {
  constructor(props) {
    super(props);
    this.state = { clubs: [] };
  }
  componentDidMount() {
    fetch('http://localhost:5000/clubs.json')
        .then((data) => data.json())
        .then((data) => this.setState({clubs: data.clubs}));
  }
  render() {
    return (
      <div><h2>Clubs</h2>
      {this.state.clubs.map((item) => {
                            return <p>{item.name}</p>; })}
      </div>
    );
  }
}
```
@[1,19](ClubsV2 class component)
@[1,19,2-5](state data)
@[1,19,2-5,6-10](use componentDidMount to fetch the data)
@[1,19,2-5,6-10,11-18](render the club data)



---
@title[Exercise]
### React.js Exercise 5

[@fa[external-link]](https://github.com/noucampdotorgRESTAPI2019/ReactJS/blob/master/exercises/ReactEx5.md)



---?color=black
@title[Title]

@snap[west headline text-white span-70]
React.js
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend
