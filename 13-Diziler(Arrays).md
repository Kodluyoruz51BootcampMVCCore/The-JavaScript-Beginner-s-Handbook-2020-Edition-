## Arrays

An array is a collection of elements.

Arrays in JavaScript are not a *type* on their own.

Arrays are **objects**.

We can initialize an empty array in these 2 different ways:

```js
const a = []
const a = Array()
```

The first is using the **array literal syntax**. The second uses the Array built-in function.

You can pre-fill the array using this syntax:

```js
const a = [1, 2, 3]
const a = Array.of(1, 2, 3)
```

An array can hold any value, even values of different types:

```js
const a = [1, 'Flavio', ['a', 'b']]
```

Since we can add an array into an array, we can create multi-dimensional arrays, which have very useful applications (e.g. a matrix):

```js
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

matrix[0][0] //1
matrix[2][0] //7
```

You can access any element of the array by referencing its index, which starts from zero:

```js
a[0] //1
a[1] //2
a[2] //3
```

You can initialize a new array with a set of values using this syntax, which first initializes an array of 12 elements, and fills each element with the number `0`:

```js
Array(12).fill(0)
```

You can get the number of elements in the array by checking its `length` property:

```js
const a = [1, 2, 3]
a.length //3
```

Note that you can set the length of the array. If you assign a bigger number than the arrays current capacity, nothing happens. If you assign a smaller number, the array is cut at that position:

```js
const a = [1, 2, 3]
a //[ 1, 2, 3 ]
a.length = 2
a //[ 1, 2 ]
```

### How to add an item to an array

We can add an element at the end of an array using the `push()` method:

```js
a.push(4)
```

We can add an element at the beginning of an array using the `unshift()` method:

```js
a.unshift(0)
a.unshift(-2, -1)
```

### How to remove an item from an array

We can remove an item from the end of an array using the `pop()` method:

```js
a.pop()
```

We can remove an item from the beginning of an array using the `shift()` method:

```js
a.shift()
```

### How to join two or more arrays

You can join multiple arrays by using `concat()`:

```js
const a = [1, 2]
const b = [3, 4]
const c = a.concat(b) //[1,2,3,4]
a //[1,2]
b //[3,4]
```

You can also use the **spread** operator (`...`) in this way:

```js
const a = [1, 2]
const b = [3, 4]
const c = [...a, ...b]
c //[1,2,3,4]
```

### How to find a specific item in the array

You can use the `find()` method of an array:

```js
a.find((element, index, array) => {
  //return true or false
})
```

Returns the first item that returns true, and returns `undefined` if the element is not found.

A commonly used syntax is:

```js
a.find(x => x.id === my_id)
```

The above line will return the first element in the array that has `id === my_id`.

`findIndex()` works similarly to `find()`, but returns the index of the first item that returns true, and if not found, it returns `undefined`:

```js
a.findIndex((element, index, array) => {
  //return true or false
})
```

Another method is `includes()`:

```js
a.includes(value)
```

Returns true if `a` contains `value`.

```js
a.includes(value, i)
```

Returns true if `a` contains `value` after the position `i`.