## Loops

Loops are one of the main control structures of JavaScript.

With a loop we can automate and repeat a block of code however many times we want it to run, even indefinitely.

JavaScript provides many way to iterate through loops.

I want to focus on 3 ways:

- while loops
- for loops
- for..of loops

### `while`

The while loop is the simplest looping structure that JavaScript provides us.

We add a condition after the `while` keyword, and we provide a block that is run until the condition evaluates to `true`.

Example:

```js
const list = ['a', 'b', 'c']
let i = 0
while (i < list.length) {
  console.log(list[i]) //value
  console.log(i) //index
  i = i + 1
}
```

You can interrupt a `while` loop using the `break` keyword, like this:

```js
while (true) {
  if (somethingIsTrue) break
}
```

and if you decide that in the middle of a loop you want to skip the current iteration, you can jump to the next iteration using `continue`:

```js
while (true) {
  if (somethingIsTrue) continue

  //do something else
}
```

Very similar to `while`, we have `do..while` loops. It's basically the same as `while`, except the condition is evaluated *after* the code block is executed.

This means the block is always executed *at least once*.

Example:

```js
const list = ['a', 'b', 'c']
let i = 0
do {
  console.log(list[i]) //value
  console.log(i) //index
  i = i + 1
} while (i < list.length)
```

### `for`

The second very important looping structure in JavaScript is the **for loop**.

We use the `for` keyword and we pass a set of 3 instructions: the initialization, the condition, and the increment part.

Example:

```js
const list = ['a', 'b', 'c']

for (let i = 0; i < list.length; i++) {
  console.log(list[i]) //value
  console.log(i) //index
}
```

Just like with `while` loops, you can interrupt a `for` loop using `break` and you can fast forward to the next iteration of a `for` loop using `continue`.

### `for...of`

This loop is relatively recent (introduced in 2015) and it's a simplified version of the `for` loop:

```js
const list = ['a', 'b', 'c']

for (const value of list) {
  console.log(value) //value
}
```