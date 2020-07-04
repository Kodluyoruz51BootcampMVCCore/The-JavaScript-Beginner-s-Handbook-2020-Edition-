## Functions

In any moderately complex JavaScript program, everything happens inside functions.

Functions are a core, essential part of JavaScript.

What is a function?

A function is a block of code, self contained.

Here's a **function declaration**:

```js
function getData() {
  // do something
}
```

A function can be run any time you want by invoking it, like this:

```js
getData()
```

A function can have one or more argument:

```js
function getData() {
  //do something
}

function getData(color) {
  //do something
}

function getData(color, age) {
  //do something
}
```

When we can pass an argument, we invoke the function passing parameters:

```js
function getData(color, age) {
  //do something
}

getData('green', 24)
getData('black')
```

Note that in the second invokation I passed the `black` string parameter as the `color` argument, but no `age`. In this case, `age` inside the function is `undefined`.

We can check if a value is not undefined using this conditional:

```js
function getData(color, age) {
  //do something
  if (typeof age !== 'undefined') {
    //...
  }
}
```

`typeof` is a unary operator that allows us to check the type of a variable.

You can also check in this way:

```js
function getData(color, age) {
  //do something
  if (age) {
    //...
  }
}
```

Although the conditional will also be true if `age` is `null`, `0` or an empty string.

You can have default values for parameters, in case they are not passed:

```js
function getData(color = 'black', age = 25) {
  //do something
}
```

You can pass any value as a parameter: numbers, strings, booleans, arrays, objects, and also functions.

A function has a return value. By default a function returns `undefined`, unless you add a `return` keyword with a value:

```js
function getData() {
  // do something
  return 'hi!'
}
```

We can assign this return value to a variable when we invoke the function:

```js
function getData() {
  // do something
  return 'hi!'
}

let result = getData()
```

`result` now holds a string with the the `hi!` value.

You can only return one value.

To return multiple values, you can return an object, or an array, like this:

```js
function getData() {
  return ['Flavio', 37]
}

let [name, age] = getData()
```

Functions can be defined inside other functions:

```js
const getData = () => {
  const dosomething = () => {}
  dosomething()
  return 'test'
}
```

The nested function cannot be called from the outside of the enclosing function.

You can return a function from a function, too.