---
title: Differences Between Functional and Class Components in React.js
shortDesc: React is a JavaScript library created by Facebook. It follows a
  declarative approach and simplifies the creation of the user interface. React
  component is a piece of isolated and reusable code used in creating a web
  application
badge: ReactJs
author: Alhazan Olajuwon
authorImage: /assets/images/image2..jpg
authorBio: Alhazan Mubarak Olajuwon Is a Frontend developer and Technical writer
  with years of experience working with ReactJS
timeRead: 7 min
date: 2022-02-27T12:14:34.657Z
tags:
  - today
image: /assets/images/react.png
imageAlt: ReactJs Components
---
### React Component

React is a JavaScript library created by Facebook. It follows a [declarative](https://medium.com/trabe/why-is-react-declarative-a-story-about-function-components-aaae83198f79) approach and simplifies the creation of the user interface. React component is a piece of isolated and reusable code used in creating a web application. There are two ways of writing components in React:

* Functional Components
* Class Components

This article will help us to understand the differences, and if to choose one over another.

### Rendering JSX

JSX means JavaScript XML. According to [React Docs](https://reactjs.org/docs/introducing-jsx.html), JSX is like a template language, which comes with the full power of JavaScript. JSX permits you to write HTML in JavaScript and place them in the DOM.

#### Rendering JSX in Functional Component

Just like the name, a functional component is a plain JavaScript function that returns a JSX

![rendering jsx functional component](/assets/images/image8.png)

If you are not familiar with an arrow function in JavaScript, here is an example below without an arrow function.

![arrow fuction ](/assets/images/image6.png)

### Rendering JSX in Class Component

A Class component is an ES6 class that extends React component which has a render method.

![](/assets/images/image5.png)

### Handling State

According to [W3schools](https://www.w3schools.com/react/react_state.asp), State is an object where you store property values that belong to the component, such that when the state changes the component re-renders.
State cannot be avoided in React Project. Until recently, handling state was only possible in class components, but in React 16.8, React Hook [UseState](https://reactjs.org/docs/hooks-state.html) was introduced which allows developers to write stateful functional components. Learn more about **Hooks** from [React Docs](https://reactjs.org/docs/hooks-intro.html).

To better understand the differences between the two components, let’s take you along to build a counter that starts from **0** and decrements by **2** on clicking the **Decrease button**.

### Project Setup

1. Create a basic react app using **npx create-react-app** counter in the terminal
2. Navigate into the folder and open it up in your favorite editor

`cd counter`

`code` .

3. Call npm start in the terminal to get the app running in the browser
4. Open **App.js** to start building the counter

### Handling State in Functional Components

Replace **App.js** with the code below:

![](/assets/images/image7.png)

When using the functional component, you need to import **UseState** hook from the React Library. This hook takes an argument of **initialState** which can be null, string or number. Then you initialize a state using array destructuring. The first variable Count in the array is the piece of state that you are keeping track of, while the second element **setCount** is a function that you call to update your piece of state. Finally, you invoke an arrow function that changes the state Count with the use of **setCount** whenever the user clicks the Decrease button.

### Handling State in Class Components

Replace **App.js** with the code below:

![](/assets/images/image4.png)

The concept is still the same, but a class component handles the state a bit differently. Firstly, you have to implement the constructor and call the super(props), only after this will state variable work. Then you initialize state object at the top containing a property called **Count** and set it to **0**. You can reference this state in the render method using **this.state.count**. 

Finally, invoke an arrow function that changes the state count using **this.setState** whenever a user clicks on the decrease button.

### Passing Props

Props are used in React to pass variables to a component. This is how you use them in both types of components.
We want to pass props of **name ="React"** and **age="8"** like below.

![Passing Props in React](/assets/images/image2.png)

You will pass props as arguments of the function in functional components. Then you will reference the props in the JSX using destructuring.

![](/assets/images/image3.png)

You can also access the props without destructing by using **props.name** and **props.age**.

![](/assets/images/image5.png)

Since it is a class, you need to use this to refer to props, and you can also use destructuring to get name inside props while utilizing class-based components.

### Component Mounting

Finally, we might want to manage component mounting and unmounting. Both can be achieved in class and functional components.
In class components, you manage the mounting through these functions:

![](/assets/images/image9.png)

**ComponentDidMount** is called immediately after the components get rendered on the DOM. **ComponentWillUnmount** is used for component teardown(i.e cleanup a particular function).
You can also achieve the same with functional component [useEffect](https://reactjs.org/docs/hooks-effect.html) Hook.

![](/assets/images/image10.png)

**UseEffect** hook is invoked with a second argument of []. The second argument of the **UseState** hook is normally an array of a state(s) that changes and **UseEffect** will be called on these selected changes. The function called first inside the **UseEffect** is the replacement for ComponentDidMount( i.e get called after components are rendered). The returned function in the **UseEffect** is the replacement for ComponentWillUnmount( i.e cleanup the first function called inside the seEffect ).

### Functional or Class components?
You have learned from this article that class and functional components have almost the same capabilities. This brings up an important question. “Which one should you learn and use”.
The answer is simply ‘both’.
If you are working with a firm that has been using React for a while, you will probably work with the Class component, because their codes were written using functional componets. On the other hand, if you are working on a new project, it might require either class or functional components.

### Conclusion
There are pros and cons in both components styles. Functional components require us to write less code, but developers that are used to object-oriented programming might prefer class components. There is little or no difference in render time between the two coding styles. So we don’t have to worry about performance issues.
In the end, it largely depends on whether we prefer an imperative object-oriented approach with classes or we appreciate declarative functional programming more.
