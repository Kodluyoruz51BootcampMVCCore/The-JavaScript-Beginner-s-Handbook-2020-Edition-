## Classes

We talked about objects, which are one of the most interesting parts of JavaScript.

In this chapter we'll go up one level by introducing classes.

What are classes? They are a way to define a common pattern for multiple objects.

Let's take a person object:

```js
const person = {
  name: 'Flavio'
}
```

We can create a class named `Person` (note the capital `P`, a convention when using classes), that has a `name` property:

```js
class Person {
  name
}
```

Now from this class, we initialize a `flavio` object like this:

```js
const flavio = new Person()
```

`flavio` is called an *instance* of the Person class.

We can set the value of the `name` property:

```js
flavio.name = 'Flavio'
```

and we can access it using

```js
flavio.name
```

like we do for object properties.

Classes can hold properties, like `name`, and methods.

Methods are defined in this way:

```js
class Person {
  hello() {
    return 'Hello, I am Flavio'
  }
}
```

and we can invoke methods on an instance of the class:

```js
class Person {
  hello() {
    return 'Hello, I am Flavio'
  }
}
const flavio = new Person()
flavio.hello()
```

There is a special method called `constructor()` that we can use to initialize the class properties when we create a new object instance.

It works like this:

```js
class Person {
  constructor(name) {
    this.name = name
  }

  hello() {
    return 'Hello, I am ' + this.name + '.'
  }
}
```

Note how we use `this` to access the object instance.

Now we can instantiate a new object from the class, pass in a string, and when we call `hello` we'll get a personalized message:

```js
const flavio = new Person('flavio')
flavio.hello() //'Hello, I am flavio.'
```

When the object is initialized, the `constructor` method is called with any parameters passed.

Normally methods are defined on the object instance, not on the class.

You can define a method as `static` to allow it to be executed on the class instead:

```js
class Person {
  static genericHello() {
    return 'Hello'
  }
}

Person.genericHello() //Hello
```

This is very useful, at times.