---
title: Why you will dare to pay me
author: debora
date: 2023-01-04 09:22:00 +0100
categories: [Tutorial, Documentation, Code Optimization]
tags: [coding, artificial intelligence, chatgpc]
render_with_liquid: false
---

This tutorial will show you how to have peer programming even if you are all alone left on the cold.

## Call out a bot

Create a new file named `YYYY-MM-DD-TITLE.EXTENSION`{: .filepath} and put it in the `_posts`{: .filepath} of the root directory. Please note that the `EXTENSION`{: .filepath} must be one of `md`{: .filepath} and `markdown`{: .filepath}. If you want to save time of creating files, please consider using the plugin [`Jekyll-Compose`](https://github.com/jekyll/jekyll-compose) to accomplish this.

## Let's show Tobby a problem

Basically, I will ask Tobby to help me with some code issues I have been facing. Specifically, I have a form with three fields which should all be required to then enable a send button. So, as my coding evolves, I would ask him: -"Tobby, transform the following property in an external function." 
I could add ", please" at the end of the sentence, but he knows me, I know him, we are intimate enough to save time worring with politeness. By the way, actually I even did not call him by his name, I just said: "Transform the following property in an external function."

```javascript
const inputOnChange={ ({ target: { value } }) => {
              setDeliveryNumber(value);
              console.log('----DELIVERY: ', deliveryNumber);
              if (deliveryNumber !== '') {
                setEntryNumberData(true);
                console.log(entryNumberData);
              } else {
                setEntryNumberData(false);
              }
            } };
```


> I could add _", please"_ at the end of the sentence, but he knows me, I know him, we are intimate enough to save time worring with politeness. By the way, actually I even did not call him by his name, I just said: _"Transform the following property in an external function."_
{: .prompt-tip }

### A master side by side to me

Well behavied than me, Tobby answers: _"Here you have a way to transform such property in external funcion:_"

```javascript
function handleInputOnChange(event) {
  const { target: { value } } = event;
  setDeliveryNumber(value);
  console.log('----DELIVERY: ', deliveryNumber);
  if (deliveryNumber !== '') {
    setEntryNumberData(true);
    console.log(entryNumberData);
  } else {
    setEntryNumberData(false);
  }
}
```
_And then, you can use it in your property the as follows:_
```javascript
const inputOnChange={handleInputOnChange}
```
_This will allow you to reuse function logic in different components or in different parts of the same component. Also, the code is easier to read and maintain since the logic is separate from the component._

I melted...
Tobby is so kind! he even did not complain about my `console.log`s!

### Can you do it? an arrow function just for me?

I had implemented all the other functions as arrow functions, I asked Tobby: "Transform this code to arrow function"

```javascript
function handleInputOnChange(event) {
  const { target: { value } } = event;
  setDeliveryNumber(value);
  console.log('----DELIVERY: ', deliveryNumber);
  if (deliveryNumber !== '') {
    setEntryNumberData(true);
    console.log(entryNumberData);
  } else {
    setEntryNumberData(false);
  }
}
```
Tobby is so patient with me...
He already knew I was talking about `handleInputOnChange`. What other code have we been discussing about? It was not needed to show it to him again...

_To turn the handleInputOnChange function into an arrow function, just replace the function keyword with an arrow (=>) and, if applicable, add parentheses around the parameters. The code would look like this:_

```javascript
const handleInputOnChange = (event) => {
  const { target: { value } } = event;
  setDeliveryNumber(value);
  console.log('----DELIVERY: ', deliveryNumber);
  if (deliveryNumber !== '') {
    setEntryNumberData(true);
    console.log(entryNumberData);
  } else {
    setEntryNumberData(false);
  }
}
```
Reading Tobby makes me realize that my French is better than my English and I thank Tobby for including extra lessons in our conversation.

_If the function has no parameters, the parentheses can be omitted. For example:_

```javascript
const handleInputOnChange = () => {
  console.log('Esta é uma função de seta sem parâmetros.');
}
```

### I had problems with the rendering of the screen

The first value is not being printed to the screen, why? it seems like there's always a late value.

In order for me to be able to help you, it would be important to see the full context in which the handleInputOnChange function is being used. Some possible reasons why the first value might not be showing are:

    The component being rendered has an initial state for the deliveryNumber, which may be displayed before the handleInputOnChange function is executed.
    The handleInputOnChange function may be triggered by an event that takes some time to fire, such as focus, which may result in a delay in refreshing the screen.

Without seeing more context, it's hard to say with certainty what the problem is. I suggest checking the initialization of the component state and also the events that are triggering the handleInputOnChange function.

### I needed to understand better the use of the useeffect in Raact
Explique-nos os estados do useeffect do react

React's useEffect hook is a function that allows you to run side effects in your component, that is, effects that occur outside the component itself, such as API calls, DOM modifications, among others.

useEffect can have three states:

    First time running: When the component is rendered for the first time, the useEffect is executed immediately after rendering.
    
    Running after updates: If the component is updated (for example, due to a change in a state or property), useEffect runs again after the update is rendered.

    Unmounting: When the component is unmounted (removed from the component tree), useEffect can be set to run again. This is useful for cleaning up any side effects the component has caused, such as canceling an ongoing API call.

To control when useEffect should be called, you can pass a list of dependencies as the function's second argument. useEffect will be executed whenever one of these dependencies changes. If the list is empty, useEffect will only be executed once, after the first rendering of the component.

Mmmm... hooks, somewhere in time I studied that. I decided to ask Tobby to rewrite my function: -"Can you change our handleInputOnChange function to use useeffect?"

Yes, it is possible to use the useEffect hook instead of the handleInputOnChange function. The handleInputOnChange function would be turned into a side effect that runs whenever the value of deliveryNumber changes.

Here is what the code would look like:



```javascript
import { useEffect } from 'react';

function MeuComponente() {
  const [deliveryNumber, setDeliveryNumber] = useState('');
  const [entryNumberData, setEntryNumberData] = useState(false);

  useEffect(() => {
    console.log('----DELIVERY: ', deliveryNumber);
    if (deliveryNumber !== '') {
      setEntryNumberData(true);
      console.log(entryNumberData);
    } else {
      setEntryNumberData(false);
    }
  }, [deliveryNumber]);

  // ... the rest of the component code
}
```


Note that the handleInputOnChange function code has been placed inside useEffect. Also, I've added a list of dependencies as the function's second argument, so that useEffect is called whenever deliveryNumber's value changes.

Now, instead of using the handleInputOnChange function as a property of an element, we can control the side effect directly in the component. This can be useful if you want to run some logic whenever the value of deliveryNumber changes, without having to worry about catching events or setting properties.
And how is the input onchange?

If you are using useEffect instead of the handleInputOnChange function, the input's onChange event can be used in the same way. The only difference is that instead of calling the handleInputOnChange function, you will need to update the value of deliveryNumber directly.

Here's what the complete code for the component would look like:

```javascript 
import { useState, useEffect } from 'react';

function MeuComponente() {
  const [deliveryNumber, setDeliveryNumber] = useState('');
  const [entryNumberData, setEntryNumberData] = useState(false);

  useEffect(() => {
    console.log('----DELIVERY: ', deliveryNumber);
    if (deliveryNumber !== '') {
      setEntryNumberData(true);
      console.log(entryNumberData);
    } else {
      setEntryNumberData(false);
    }
  }, [deliveryNumber]);

  return (
    <input
      value={deliveryNumber}
      onChange={({ target: { value } }) => setDeliveryNumber(value)}
    />
  );
}
```
Now, when typing something in the input, the value of deliveryNumber will be updated and the useEffect will be executed, changing the value of entryNumberData and displaying the messages in the console.

### There would be alternatives to the use of states?

Better to explore. Again, I turnet to Tobby: "Explain to me the useState, and show me what are the other alternatives to it, if."

The useState hook is a React function that allows you to add state to your functional components. It returns a pair of values: the current state and a function to update it.

For example, here's how useState is used to add count state to a component:

```javascript
import { useState } from 'react';

function MeuComponente() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>O valor atual é {count}</p>
      <button onClick={() => setCount(count + 1)}>Incrementar</button>
    </div>
  );
}
```
In the example above, the component has the count state, initially set to 0, and the setCount function to update it. When the button is clicked, the function is called to increment the count value.

useState is an alternative to using classes to create stateful components. Rather than creating a class and writing methods to manage state, you can useState in functional components to achieve the same result.

Other alternatives for managing state in React components are Redux and the Context API. These tools are more advanced and allow you to manage state in larger applications, but they require more configuration and can be more complex to work with. useState is a simpler and easier to use option, especially in small applications or in isolated components.
What if it was emm Context API? how would it be?

If you wanted to use the Context API to manage state instead of useState, the code would look something like this:



```javascript
import { createContext, useContext } from 'react';

// Cria o contexto
const CountContext = createContext();

function MeuComponente() {
  // Consome o contexto
  const [count, setCount] = useContext(CountContext);

  return (
    <div>
      <p>O valor atual é {count}</p>
      <button onClick={() => setCount(count + 1)}>Incrementar</button>
    </div>
  );
}

function App() {
  const [count, setCount] = useState(0);

  return (
    // Fornece o contexto
    <CountContext.Provider value={[count, setCount]}>
      <MeuComponente />
    </CountContext.Provider>
  );
}
```
In the code above, we created a context called CountContext and provided it to the MyComponent component as a provider. The component then consumes the context with useContext and gets the current value and the function to update it.

Unlike useState, the Context API allows you to share state between components that are in different parts of the component tree, without having to pass props manually from parent to child. This can be useful in larger applications, but it requires more setup and can be a bit more complex to work with. useState is a simpler and easier to use option, especially in small applications or in isolated components.
starambients@gmail.com
And if it was in Redux, how would it look?

If you wanted to use Redux to manage state instead of useState, the code would look something like this:


```javascript
import { connect } from 'react-redux';

function MeuComponente(props) {
  const { count, incrementCount } = props;

  return (
    <div>
      <p>O valor atual é {count}</p>
      <button onClick={incrementCount}>Incrementar</button>
    </div>
  );
}

// Mapeia o estado do Redux para as props do componente
const mapStateToProps = (state) => ({
  count: state.count
});

// Mapeia as actions do Redux para as props do componente
const mapDispatchToProps = (dispatch) => ({
  incrementCount: () => dispatch({ type: 'INCREMENT' })
});

export default connect(mapStateToProps, mapDispatchToProps)(MeuComponente);
```
In the code above, we used connect from react-redux to map Redux state and actions to component props. Next, we pass the component as an argument to connect, which returns a new component enriched with the mapped props.

Redux is a powerful tool for managing state in larger applications, but it requires more configuration and can be more complex to work with. useState is a simpler and easier to use option, especially in small applications or in isolated components.