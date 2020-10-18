---
layout: post
title:      "Reacting to Components!"
date:       2020-10-18 22:52:42 +0000
permalink:  reacting_to_components
---


The world of React is mighty and many have fallen....ok, thats dramatic. But in all seriousness, there is a lot to take in with React. The first thing that began to help me in wrapping my brain around React was realizing that it is a Javascript library and all the code is JS. For example, looking at JSX helped me to understand this a lot more. 

```function catName(cat) {
  return cat.Name;
}

const cat = {
  Name: 'Garfield',
  
};

const element = (
  <h1>
    Hello, {catName(cat)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);```

Here I am creating a function that takes in a name and then displays that name. With JSX, I am able to call that function using curly brackets. This way I can directly call the function in an h1. Pretty cool.
Now, if we take a look at the bottom of the code, we notice something interesting. What is exactly going on with the DOM there? Here we are rendering the const element onto the DOM and we are using an id of root to display it. This would mean that somewhere in an html file is most liekly a div with the id of root. We are then able to see "Hello, Garfield" as an h1 on the page.

This brings us to components. The easiest way to define a component is to build a JS function. For example:

```function Howdy(props) {
  return <h1>Howdy {props.name}</h1>;
}```

This is a React component because it accepts a single props object argument with data and returns a React element. This is why you will hear these referred to as "functional components", they are actaully JS functions. 
So how would we render a component?  Well, lets look at the code. 
Lets say I build a function that says Howdy to whatever name is passed in. 

```function Howdy(props) {
  return <h1>Howdy, {props.name}</h1>;
}```

I would then declare an element that represents a user defined component.

```const element = <Howdy name="Jimmy" />;```

So if React sees an element that contains a user-defined component, it will pass that JSX attributes and children to this component as a single object and that object is called props. So what does that mean?

```function Howdy(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Howdy name="Jimmy" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);```

In this code, React will look at the const element and see that it contains name="Jimmy" and that that is a user-defined component. It will then send that as an object to the function Howdy because we also called Howdy before that. So "Jimmy" will go to the Howdy function as props and the Howdy function wil go through its execution and render "Howdy, Jimmy" as an h1 in the DOM. 

There is a lot to unpack here and this blog only touches on how React works. This is only the beginning and it will be a great adventure.




