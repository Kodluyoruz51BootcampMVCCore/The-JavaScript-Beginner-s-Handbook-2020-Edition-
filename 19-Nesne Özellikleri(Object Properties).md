## Object Properties

Objects have **properties**, which are composed by a label associated with a value.

The value of a property can be of any type, which means that it can be an array, a function, and it can even be an object, as objects can nest other objects.

This is the object literal syntax we saw in the previous chapter:

```js
const car = {

}
```

We can define a `color` property in this way:

```js
const car = {
  color: 'blue'
}
```

Here we have a `car` object with a property named `color`, with value `blue`.

Labels can be any string, but beware of special characters - if I wanted to include a character not valid as a variable name in the property name, I would have had to use quotes around it:

```js
const car = {
  color: 'blue',
  'the color': 'blue'
}
```

Invalid variable name characters include spaces, hyphens, and other special characters.

As you can see, when we have multiple properties, we separate each property with a comma.

We can retrieve the value of a property using 2 different syntaxes.

The first is **dot notation**:

```js
car.color //'blue'
```

The second (which is the only one we can use for properties with invalid names), is to use square brackets:

```js
car['the color'] //'blue'
```

If you access a nonexistant property, you'll get the `undefined` value:

```js
car.brand //undefined
```

As mentioned before, objects can have nested objects as properties:

```js
const car = {
  brand: {
    name: 'Ford'
  },
  color: 'blue'
}
```

In this example, you can access the brand name using

```js
car.brand.name
```

or

```js
car['brand']['name']
```

You can set the value of a property when you define the object.

But you can always update it later on:

```js
const car = {
  color: 'blue'
}

car.color = 'yellow'
car['color'] = 'red'
```

And you can also add new properties to an object:

```js
car.model = 'Fiesta'

car.model //'Fiesta'
```

Given the object

```js
const car = {
  color: 'blue',
  brand: 'Ford'
}
```

you can delete a property from this object using

```js
delete car.brand
```