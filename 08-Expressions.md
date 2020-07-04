## Expressions

An expression is a single unit of JavaScript code that the JavaScript engine can evaluate, and return a value.

Expressions can vary in complexity.

We start from the very simple ones, called primary expressions:

```js
2
0.02
'something'
true
false
this //the current scope
undefined
i //where i is a variable or a constant
```

Arithmetic expressions are expressions that take a variable and an operator (more on operators soon), and result in a number:

```js
1 / 2
i++
i -= 2
i * 2
```

String expressions are expressions that result in a string:

```js
'A ' + 'string'
```

Logical expressions make use of logical operators and resolve to a boolean value:

```js
a && b
a || b
!a
```

More advanced expressions involve objects, functions, and arrays, and I'll introduce them later.