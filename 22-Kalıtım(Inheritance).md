## Inheritance

A class can **extend** another class, and objects initialized using that class inherit all the methods of both classes.

Suppose we have a class `Person`:

```js
class Person {
  hello() {
    return 'Hello, I am a Person'
  }
}
```

We can define a new class, `Programmer`, that extends `Person`:

```js
class Programmer extends Person {

}
```

Now if we instantiate a new object with the class `Programmer`, it has access to the `hello()` method:

```js
const flavio = new Programmer()
flavio.hello() //'Hello, I am a Person'
```

Inside a child class, you can reference the parent class by calling `super()`:

```js
class Programmer extends Person {
  hello() {
    return super.hello() + 
      '. I am also a programmer.'
  }
}

const flavio = new Programmer()
flavio.hello()
```

The above program prints *Hello, I am a Person. I am also a programmer.*.