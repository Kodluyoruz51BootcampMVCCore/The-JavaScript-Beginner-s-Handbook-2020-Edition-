## Objects

Any value that's not of a primitive type (a string, a number, a boolean, a symbol, null, or undefined) is an **object**.

Here's how we define an object:

```js
const car = {

}
```

This is the **object literal** syntax, which is one of the nicest things in JavaScript.

You can also use the `new Object` syntax:

```js
const car = new Object()
```

Another syntax is to use `Object.create()`:

```js
const car = Object.create()
```

You can also initialize an object using the `new` keyword before a function with a capital letter. This function serves as a constructor for that object. In there, we can initialize the arguments we receive as parameters, to setup the initial state of the object:

```js
function Car(brand, model) {
  this.brand = brand
  this.model = model
}
```

We initialize a new object using:

```js
const myCar = new Car('Ford', 'Fiesta')
myCar.brand //'Ford'
myCar.model //'Fiesta'
```

Objects are **always passed by reference**.

If you assign a variable the same value of another, if it's a primitive type like a number or a string, they are passed by value:

Take this example:

```js
let age = 36
let myAge = age
myAge = 37
age //36
const car = {
  color: 'blue'
}
const anotherCar = car
anotherCar.color = 'yellow'
car.color //'yellow'
```

Even arrays or functions are, under the hood, objects, so it's very important to understand how they work.