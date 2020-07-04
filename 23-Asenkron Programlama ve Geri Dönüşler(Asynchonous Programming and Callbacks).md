## Asynchonous Programming and Callbacks

Most of the time, JavaScript code is run synchronously.

This means that a line of code is executed, then the next one is executed, and so on.

Everything is as you expect, and how it works in most programming languages.

However, there are times when you cannot just wait for a line of code to execute.

You can't just wait 2 seconds for a big file to load, and halt the program completely.

You can't just wait for a network resource to be downloaded before doing something else.

JavaScript solves this problem by using **callbacks**.

One of the simplest examples of how to use callbacks is with timers. Timers are not part of JavaScript, but they are provided by the browser and Node.js. Let me talk about one of the timers we have: `setTimeout()`.

The `setTimeout()` function accepts 2 arguments: a function, and a number. The number is the milliseconds that must pass before the function is ran.

Example:

```js
setTimeout(() => {
  // runs after 2 seconds
  console.log('inside the function')
}, 2000)
```

The function containing the `console.log('inside the function')` line will be executed after 2 seconds.

If you add a `console.log('before')` prior to the function, and `console.log('after')` after it:

```js
console.log('before')
setTimeout(() => {
  // runs after 2 seconds
  console.log('inside the function')
}, 2000)
console.log('after')
```

You will see this happening in your console:

```js
before
after
inside the function
```

The callback function is executed asynchronously.

This is a very common pattern when working with the file system, the network, events, or the DOM in the browser.

All of the things I mentioned are not "core" JavaScript, so they are not explained in this handbook, but you'll find lots of examples in my other handbooks available at [https://flaviocopes.com](https://flaviocopes.com/).

Here's how we can implement callbacks in our code.

We define a function that accepts a `callback` parameter, which is a function.

When the code is ready to invoke the callback, we invoke it by passing the result:

```js
const doSomething = callback => {
  //do things
  //do things
  const result = /* .. */
  callback(result)
}
```

Code using this function would use it like this:

```js
doSomething(result => {
  console.log(result)
})
```