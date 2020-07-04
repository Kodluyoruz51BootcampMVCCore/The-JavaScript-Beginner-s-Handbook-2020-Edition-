## Comparison operators

After assignment and math operators, the third set of operators I want to introduce is conditional operators.

You can use the following operators to compare two numbers, or two strings.

Comparison operators always return a boolean, a value that's `true` or `false`).

Those are **disequality comparison operators**:

- `<` means "less than"
- `<=` means "less than or equal to"
- `>` means "greater than"
- `>=` means "greater than or equal to"

Example:

```js
let a = 2
a >= 1 //true
```

In addition to those, we have 4 **equality operators**. They accept two values, and return a boolean:

- `===` checks for equality
- `!==` checks for inequality

Note that we also have `==` and `!=` in JavaScript, but I highly suggest to only use `===` and `!==` because they can prevent some subtle problems.