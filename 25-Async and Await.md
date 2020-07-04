## Async and Await

Async functions are a higher level abstraction of promises.

An async function returns a promise, like in this example:

```js
const getData = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => 
      resolve('some data'), 2000)
  })
}
```

Any code that wants to use this function will use the `await` keyword right before the function:

```js
const data = await getData()
```

and doing so, any data returned by the promise is going to be assigned to the `data` variable.

In our case, the data is the "some data" string.

With one particular caveat: whenever we use the `await` keyword, we must do so inside a function defined as `async`.

Like this:

```js
const doSomething = async () => {
  const data = await getData()
  console.log(data)
}
```

The async/await duo allows us to have a cleaner code and a simple mental model to work with asynchronous code.

As you can see in the example above, our code looks very simple. Compare it to code using promises, or callback functions.

And this is a very simple example, the major benefits will arise when the code is much more complex.

As an example, here's how you would get a JSON resource using the Fetch API, and parse it, using promises:

```js
const getFirstUserData = () => {
  // get users list
  return fetch('/users.json') 
    // parse JSON
    .then(response => response.json()) 
    // pick first user
    .then(users => users[0]) 
    // get user data
    .then(user => 
      fetch(`/users/${user.name}`)) 
    // parse JSON
    .then(userResponse => response.json()) 
}

getFirstUserData()
```

And here is the same functionality provided using await/async:

```js
const getFirstUserData = async () => {
  // get users list
  const response = await fetch('/users.json') 
  // parse JSON
  const users = await response.json() 
  // pick first user
  const user = users[0] 
  // get user data
  const userResponse = 
    await fetch(`/users/${user.name}`)
  // parse JSON
  const userData = await user.json() 
  return userData
}

getFirstUserData()
```