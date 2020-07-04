## Variables

A variable is a value assigned to an identifier, so you can reference and use it later in the program.

This is because JavaScript is **loosely typed**, a concept you'll frequently hear about.

A variable must be declared before you can use it.

We have 2 main ways to declare variables. The first is to use `const`:

```js
const a = 0
```

The second way is to use `let`:

```js
let a = 0
```

What's the difference?

`const` defines a constant reference to a value. This means the reference cannot be changed. You cannot reassign a new value to it.

Using `let` you can assign a new value to it.

For example, you cannot do this:

```js
const a = 0
a = 1
```

Because you'll get an error: `TypeError: Assignment to constant variable.`.

On the other hand, you can do it using `let`:

```js
let a = 0
a = 1
```

`const` does not mean "constant" in the way some other languages like C mean. In particular, it does not mean the value cannot change - it means it cannot be reassigned. If the variable points to an object or an array (we'll see more about objects and arrays later) the content of the object or the array can freely change.

`const` variables must be initialized at the declaration time:

```js
const a = 0
```

but `let` values can be initialized later:

```js
let a
a = 0
```

You can declare multiple variables at once in the same statement:

```js
const a = 1, b = 2
let c = 1, d = 2
```

But you cannot redeclare the same variable more than one time:

```js
let a = 1
let a = 2
```

or you'd get a "duplicate declaration" error.

My advice is to always use `const` and only use `let` when you know you'll need to reassign a value to that variable. Why? Because the less power our code has, the better. If we know a value cannot be reassigned, it's one less source for bugs.

Now that we saw how to work with `const` and `let`, I want to mention `var`.

Until 2015, `var` was the only way we could declare a variable in JavaScript. Today, a modern codebase will most likely just use `const` and `let`. There are some fundamental differences which I detail [in this post](https://flaviocopes.com/javascript-difference-let-var/) but if you're just starting out, you might not care about them. Just use `const` and `let`.

