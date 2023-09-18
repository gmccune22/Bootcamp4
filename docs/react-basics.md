# React Basics

[**React**](https://reactjs.org/) is a JavaScript library for building user interfaces. Created by Facebook, Instagram, and the community, React is the V is View in the MVC architecture. React uses a component-based architecture to implement and manage the View of a web applciation.

React makes it (relatively) easy to start building an application by extending HTML so that the markup can describe not only the static webpage but also dynamic behavior.

Note: Outside of the pure React library itself, there are 3 distinct versions of React: React-devtools, ReactJS.Net, React Native. Other than React itself, React Native is pretty popular as well for creating Native mobile apps. However, we will be using React.js.

## JSX

React uses its own flavor of Javascript called JSX. JSX allows us to describe our User Interfaces (UIs) in a syntax very close to the HTML that we are used to. It is, however, optional. React can be used without JSX. In fact, React just compiles JSX to pure JavaScript. Then it works with compiled JavaScript in the browser.

To get a basic introduction to JSX [**see the docs here**](https://reactjs.org/docs/introducing-jsx.html) and find a more in-depth tutorial on JSX [**here**](https://reactjs.org/docs/jsx-in-depth.html). In most cases, we will use JSX instead of Javascript to develop our application.

## React Components

[**React Components**](https://www.freecodecamp.org/news/how-to-write-your-first-react-js-component-d728d759cabc/) are the basic building blocks of a React Application. As you think about the UI of your web application, identify aspects of your UI that are used several times (Button, Panel, Avatar), or are complex enough on its own (App, FeedStory, Comment). These are good candidates for reusable components you should develop.  

React components are small, reusable pieces of code that return a React element to be rendered to the page. A component can be broken down into distinct pieces of functionality and used within other components. Components can return other components, arrays, strings and numbers.

A React component can be one of two types: (1) a function (or functional) component or (2) a class component. Sometimes you will hear different terms to describe these two types, like stateless and stateful. Function components are stateless and are often associated with the presentational concept. Class components are stateful.

The simplest version of React component is a plain JavaScript function that returns a React element:

```Javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Function components take in props (i.e., data), and output to the DOM. It returns what looks like HTML, but is really a special JavaScript syntax called JSX.

Components can also be ES6 classes

```Javascript
class Hello extends React.Component {
    render() {
        return <h1> Hello, {this.props.name}</h1>;
      }
} 
ReactDOM.render(<Hello />, mountNode);
```

This code creates a simple Hello Component and renders a modified `<h1>` tag and the name of the person passed in from another component.

## Managing State and Lifecycle Events

Function and class components manage state. State is a JavaScript object that stores a component's dynamic data and determines the component's behavior. State is private and fully controlled by the component. It is not accessible to any component other than the one that owns and sets it. State can be passed to child components as props, but it is not accessible to parent components. This private internal state is what gives React its reactive nature. When the state changes, React will re-render that component in the browser.

While function components use functions called hooks to manage state, class components use lifecycle methods. Lifecycle methods are methods that are called at different stages of a component's life. For example, the `componentDidMount()` method is called after a component is rendered to the DOM. The `componentDidUpdate()` method is called after a component's state or props change. The `componentWillUnmount()` method is called just before a component is removed from the DOM. These methods can be used to perform actions based on the component's state.

Since 2019, function components have become the more popular way to define a React component. Function components are simpler to write, easier to test, and help maintain best practices.

[**Anatomy of a React Componnent**](https://codeburst.io/react-state-vs-props-explained-51beebd73b21)

[React Components](https://reactjs.org/docs/react-component.html)  
Component names should also always start with a capital letter (`<Wrapper/> not <wrapper/>`). See [**documentation**](https://reactjs.org/docs/components-and-props.html#rendering-a-component) for more information on rendering components.

## Component Communication - State vs Props

In a React component, props carry data around your application. Props are variables passed to it by its parent component. State on the other hand are also variables, but directly initialized and managed by the component. The state can be initalized by props.

The State and Props objects have one important difference. Inside a class component, the State object can be changed while the Props object represents fixed values.

For example, a parent component might include a child component by calling

```Javascript
<ChildComponent />
````

The parent can pass a prop by using this syntax:

```Javascript
<ChildComponent color=green/>
````

Inside the ChildComponent constructor, we could access the `color` prop:

```Javascript
function ChildComponent(props) {
  console.log(props.color) // prints green
}
````

or

```Javascript
function ChildComponent({ color }) {
  console.log(color) // prints green
}
```

And any other method in this class can reference the props using the exampled syntax.

However, props should **never** be changed in a child component, so if there’s something going on that alters some variable, that variable should belong to the component state.

Props are also used to allow child components to access methods defined in the parent component. This is a good way to centralize managing the state in the parent component, and avoid children to have the need to have their own state.

Most of your components will just display some kind of information based on the props they received, and stay stateless.

## Getting Started with React

React certainly has a learning curve, and you should take some time going through tutorials to understand the basics. Below is a list of concepts and resources that may be helpful.

- [**React Vocabulary**](https://reactjs.org/docs/glossary.html) - This is a must read as you are working though the assignment and tutorials.

- [**Thinking in React**](https://reactjs.org/docs/thinking-in-react.html) - This gives you an overview and philosophy for developing in React.

- [**React Developer Tools**](https://www.freecodecamp.org/news/how-to-see-your-react-state-props-in-the-browser-774098a50fcc/) Download the React Developer Tools Chrome Plug-in to help you debug your application or use the Chrome Developer Tools