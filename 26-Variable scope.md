## Variable scope

When I introduced variables, I talked about using `const`, `let`, and `var`.

Scope is the set of variables that's visible to a part of the program.

In JavaScript we have a global scope, block scope and function scope.

If a variable is defined outside of a function or block, it's attached to the global object and it has a global scope, which mean it's available in every part of a program.

There is a very important difference between `var`, `let` and `const` declarations.

A variable defined as `var` inside a function is only visible inside that function, similar to a function's arguments.

A variable defined as `const` or `let` on the other hand is only visible inside the **block** where it is defined.

A block is a set of instructions grouped into a pair of curly braces, like the ones we can find inside an `if` statement, a `for` loop, or a function.

It's important to understand that a block does not define a new scope for `var`, but it does for `let` and `const`.

This has very practical implications.

Suppose you define a `var` variable inside an `if` conditional in a function

```js
function getData() {
  if (true) {
    var data = 'some data'
    console.log(data) 
  }
}
```

If you call this function, you'll get `some data` printed to the console.

If you try to move console.log(data) after the `if`, it still works:

```js
function getData() {
  if (true) {
    var data = 'some data'
  }
  console.log(data) 
}
```

But if you switch `var data` to `let data`:

```js
function getData() {
  if (true) {
    let data = 'some data'
  }
  console.log(data) 
}
```

You'll get an error: `ReferenceError: data is not defined`.

This is because `var` is function scoped, and there's a special thing happening here called hoisting. In short, the `var` declaration is moved to the top of the closest function by JavaScript before it runs the code. This is what the function looks like to JS internally, more or less:

```js
function getData() {
  var data
  if (true) {
    data = 'some data'
  }
  console.log(data) 
}
```

This is why you can also `console.log(data)` at the top of a function, even before it's declared, and you'll get `undefined` as a value for that variable:

```js
function getData() {
  console.log(data) 
  if (true) {
    var data = 'some data'
  }
}
```

but if you switch to `let`, you'll get an error `ReferenceError: data is not defined`, because hoisting does not happen to `let` declarations.

`const` follows the same rules as `let`: it's block scoped.

It can be tricky at first, but once you realize this difference, then you'll see why `var` is considered a bad practice nowadays compared to `let` - they have less moving parts, and their scope is limited to the block, which also makes them very good as loop variables because they cease to exist after a loop has ended:

```js
function doLoop() {
  for (var i = 0; i < 10; i++) {
    console.log(i)
  }
  console.log(i)
}

doLoop()
```

When you exit the loop, `i` will be a valid variable with value 10.

If you switch to `let`, when you try to `console.log(i)` will result in an error `ReferenceError: i is not defined`.
