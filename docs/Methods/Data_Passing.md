# Data Passing

In React, we often encounter the need for components to communicate with each other. 
The essence of a component is a function. 
When calling a component, we can pass the required variables to another component like passing parameters. 
The most natural way to pass parameters is from parent component to child component, 
but many times what we need is to pass variables between sibling components. 
The solution to achieve this kind of variable passing is
to use `useState()` in the parent component of the sibling component 
(or create a new one if it doesn't exist) to define a variable and its setter and pass it to the child component. 
In the child component, you can use setters to change the value of the variable,
and listen to whether the value of the child component changes to re-render the component.

## Pass By `props.state`

We tried many ways to pass variables between components, 
but we finally decide using the most basic way, that is using props as the main method. 
Because using props is simple and robust, and there is no black box.
Here are some example we use to pass variables by props.

#### 1. Base case
Put the param in Child component's state field,
the param could be define previously or directly assign a value in state.

<details><summary>Example</summary>

in Parent.js

```javascript
export function Parent(props){
  const [param1, setParam1] = useState("Base example")
  return (
    <Child state={{param1, setParam1, constParam: "const param"}} >
      "Children"
    </Child>
  )
}
```

in Child.js

```javascript
export function Child(props){
  const{param1, setParam1, constParam} = props.state
  const children = props.children
  return `${children} ${param1} ${constParam}`;
}
```
</details>

----------

#### 2. Partially Using State

You are not necessary to get all the params from state, 
and you can rename it

<details><summary>Example</summary>

in Parent.js

```javascript
export function Parent(props){
  const [param1, setParam1] = useState("example 2")

  return (
    <Child state={{param1, setParam1}} />
  )
}
```

in Child.js

```javascript
export function Child(props){
  const{param1: myParam} = props.state

  return myParam;
}
```
</details>

--------

#### 3. Package The State

You can package all the state and pass it to multiple children,
And Child can only get the param their need.

<details><summary>Example</summary>

in Parent.js

```javascript
export function Parent(props){
  
  const [param1, setParam1] = useState("example 3 param1")
  const [param2, setParam2] = useState("example 3 param2")

  const state={param1, setParam1, param2, setParam2}

  return (
    <>
      <Child1 state={state} />
      <Child2 state={state} />
    </>
  )
}
```

in Child1.js

```javascript
export function Child1(props){
  const{param1, setParam1} = props.state

  return param1;
}
```

in Child2.js

```javascript
export function Child2(props){
  const{param2, setParam2} = props.state

  return param2;
}
```

</details>

--------

#### 4. Package The State

You can use `{...props.state}` to pass all inherited state.

<details><summary>Example</summary>

in GrandParent.js

```javascript
export function GrandParent(props){
  const [grandParam, setGrandParam] = useState("example 4")

  return (
    <Parent state={{grandParam, setGrandParam}} />
  )
}
```

in Parent.js

```javascript
export function Parent(props){
  return (
    <Child state={{...props.state}} />
  )
}
```

in Child.js

```javascript
export function Child(props){
  const{grandParam, setGrandParam} = props.state

  return grandParam;
}
```

</details>

--------

#### 5. Combination

The above methods can be combined with each other.

<details><summary>Example</summary>

in GrandParent.js

```javascript
export function GrandParent(props){
  const [grandParam, setGrandParam] = useState("example 5")

  return (
    <Parent state={{grandParam, setGrandParam}} />
  )
}
```

in Parent.js

```javascript
export function Parent(props){
  const [parentParam1, setParentParam1] = useState("parent param 1")
  const [parentParam2, setParentParam2] = useState("parent param 2")

  const state = {parentParam1, parentParam2}
  return (
    <Child state={{...props.state, ...state, constParam: "const param"}} />
  )
}
```

in Child.js

```javascript
export function Child(props){
  const{grandParam, parentParam1, parentParam2, constParam} = props.state

  return `${grandParam}, ${parentParam1}, ${parentParam2}, ${constParam}`;
}
```

</details>

--------

## Pass By Context

When the nesting relationship of components is too complex to use props,
we will use context to pass parameters. 
But once the context is used, 
it means that the components connected by the context will become inseparable, 
it will reducing the modularity of the code.