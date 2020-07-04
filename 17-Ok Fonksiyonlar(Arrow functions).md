## Arrow functions

Arrow functions are a recent introduction to JavaScript.

They are very often used instead of "regular" functions, the ones I described in the previous chapter. You'll find both forms used everywhere.

Visually, they allows you to write functions with a shorter syntax, from:

```js
function getData() {
  //...
}
```

to

```js
() => {
  //...
}
```

But.. notice that we don't have a name here.

Arrow functions are anonymous. We must assign them to a variable.

We can assign a regular function to a variable, like this:

```js
let getData = function getData() {
  //...
}
```

When we do so, we can remove the name from the function:

```js
let getData = function() {
  //...
}
```

and invoke the function using the variable name:

```js
let getData = function() {
  //...
}
getData()
```

That's the same thing we do with arrow functions:

```js
let getData = () => {
  //...
}
getData()
```

If the function body contains just a single statement, you can omit the parentheses and write everything on a single line:

```js
const getData = () => console.log('hi!')
```

Parameters are passed in the parentheses:

```js
const getData = (param1, param2) => 
  console.log(param1, param2)
```

If you have one (and just one) parameter, you could omit the parentheses completely:

```js
const getData = param => console.log(param)
```

Arrow functions allow you to have an implicit return - values are returned without having to use the `return` keyword.

It works when there is a one-line statement in the function body:

```js
const getData = () => 'test'

getData() //'test'
```

Like with regular functions, we can have default values for parameters in case they are not passed:

```js
const getData = (color = 'black', 
                 age = 2) => {
  //do something
}
```

And like regular functions, we can only return one value.

Arrow functions can also contain other arrow functions, or even regular functions.

The two types of functions are very similar, so you might ask why arrow functions were introduced. The big difference with regular functions is when they are used as object methods. This is something we'll soon look into.