## Object Methods

I talked about functions in a previous chapter.

Functions can be assigned to a function property, and in this case they are called **methods**.

In this example, the `start` property has a function assigned, and we can invoke it by using the dot syntax we used for properties, with the parentheses at the end:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: function() {
    console.log('Started')
  }
}

car.start()
```

Inside a method defined using a `function() {}` syntax we have access to the object instance by referencing `this`.

In the following example, we have access to the `brand` and `model` properties values using `this.brand` and `this.model`:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: function() {
    console.log(`Started 
      ${this.brand} ${this.model}`)
  }
}

car.start()
```

It's important to note this distinction between regular functions and arrow functions - we don't have access to `this` if we use an arrow function:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: () => {
    console.log(`Started 
      ${this.brand} ${this.model}`) //not going to work
  }
}

car.start()
```

This is because **arrow functions are not bound to the object**.

This is the reason why regular functions are often used as object methods.

Methods can accept parameters, like regular functions:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  goTo: function(destination) {
    console.log(`Going to ${destination}`)
  }
}

car.goTo('Rome')
```