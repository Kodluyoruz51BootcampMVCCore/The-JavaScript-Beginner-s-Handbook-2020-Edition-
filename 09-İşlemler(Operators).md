## Operators

Operators allow you to get two simple expressions and combine them to form a more complex expression.

We can classify operators based on the operands they work with. Some operators work with 1 operand. Most work with 2 operands. Just one operator works with 3 operands.

In this first introduction to operators, we'll introduce the operators you are most likely familiar with: operators with 2 operands.

I already introduced one when talking about variables: the assignment operator `=`. You use `=` to assign a value to a variable:

```js
let b = 2
```

Let's now introduce another set of binary operators that you're already familiar with from basic math.

### The addition operator (+)

```js
const three = 1 + 2
const four = three + 1
```

The `+` operator also does string concatenation if you use strings, so pay attention:

```js
const three = 1 + 2
three + 1 // 4
'three' + 1 // three1
```

### The subtraction operator (-)

```js
const two = 4 - 2
```

### The division operator (/)

Returns the quotient of the first operator and the second:

```js
const result = 20 / 5 //result === 4
const result = 20 / 7 //result === 2.857142857142857
```

If you divide by zero, JavaScript does not raise any error but returns the `Infinity` value (or `-Infinity` if the value is negative).

```js
1 / 0 //Infinity
-1 / 0 //-Infinity
```

### The remainder operator (%)

The remainder is a very useful calculation in many use cases:

```js
const result = 20 % 5 //result === 0
const result = 20 % 7 //result === 6
```

A remainder by zero is always `NaN`, a special value that means "Not a Number":

```js
1 % 0 //NaN
-1 % 0 //NaN
```

### The multiplication operator (*)

Multiply two numbers

```js
1 * 2 //2
-1 * 2 //-2
```

### The exponentiation operator (**)

Raise the first operand to the power of the second operand

```js
1 ** 2 //1
2 ** 1 //2
2 ** 2 //4
2 ** 8 //256
8 ** 2 //64
```