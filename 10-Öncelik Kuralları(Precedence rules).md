## Precedence rules

Every complex statement with multiple operators in the same line will introduce precedence problems.

Take this example:

```js
let a = 1 * 2 + 5 / 2 % 2
```

The result is 2.5, but why?

What operations are executed first, and which need to wait?

Some operations have more precedence than the others. The precedence rules are listed in this table:

| OPERATOR    | DESCRIPTION             |
| :---------- | :---------------------- |
| `*` `/` `%` | multiplication/division |
| `+` `-`     | addition/subtraction    |
| `=`         | assignment              |

Operations on the same level (like `+` and `-`) are executed in the order they are found, from left to right.

Following these rules, the operation above can be solved in this way:

```js
let a = 1 * 2 + 5 / 2 % 2
let a = 2 + 5 / 2 % 2
let a = 2 + 2.5 % 2
let a = 2 + 0.5
let a = 2.5
```