## Promises

Promises are an alternative way to deal with asynchronous code.

As we saw in the previous chapter, with callbacks we'd be passing a function to another function call that would be called when the function has finished processing.

Like this:

```js
doSomething(result => {
  console.log(result)
})
```

When the `doSomething()` code ends, it calls the function received as a parameter:

```js
const doSomething = callback => {
  //do things
  //do things
  const result = /* .. */
  callback(result)
}
```

The main problem with this approach is that if we need to use the result of this function in the rest of our code, all our code must be nested inside the callback, and if we have to do 2-3 callbacks we enter in what is usually defined "callback hell" with many levels of functions indented into other functions:

```js
doSomething(result => {
  doSomethingElse(anotherResult => {
    doSomethingElseAgain(yetAnotherResult => {
      console.log(result)
    })
  }) 
})
```

Promises are one way to deal with this.

Instead of doing:

```js
doSomething(result => {
  console.log(result)
})
```

We call a promise-based function in this way:

```js
doSomething()
  .then(result => {
    console.log(result)
  })
```

We first call the function, then we have a `then()` method that is called when the function ends.

The indentation does not matter, but you'll often use this style for clarity.

It's common to detect errors using a `catch()` method:

```js
doSomething()
  .then(result => {
    console.log(result)
  })
  .catch(error => {
    console.log(error)
  })
```

Now, to be able to use this syntax, the `doSomething()` function implementation must be a little bit special. It must use the Promises API.

Instead of declaring it as a normal function:

```js
const doSomething = () => {
  
}
```

We declare it as a promise object:

```js
const doSomething = new Promise()
```

and we pass a function in the Promise constructor:

```js
const doSomething = new Promise(() => {

})
```

This function receives 2 parameters. The first is a function we call to resolve the promise, the second a function we call to reject the promise.

```js
const doSomething = new Promise(
  (resolve, reject) => {
    
})
```

Resolving a promise means to complete it successfully (which results in calling the `then()` method in whatever uses it).

Rejecting a promise means ending it with an error (which results in calling the `catch()` method in whatever uses it).

Here's how:

```js
const doSomething = new Promise(
  (resolve, reject) => {
    //some code
    const success = /* ... */
    if (success) {
      resolve('ok')
    } else {
      reject('this error occurred')
    }
  }
)
```

We can pass a parameter to the resolve and reject functions, of any type we want.