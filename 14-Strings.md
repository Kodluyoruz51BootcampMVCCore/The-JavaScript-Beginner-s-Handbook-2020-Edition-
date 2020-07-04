## Strings

A string is a sequence of characters.

It can be also defined as a string literal, which is enclosed in quotes or double quotes:

```js
'A string'
"Another string"
```

I personally prefer single quotes all the time, and use double quotes only in HTML to define attributes.

You assign a string value to a variable like this:

```js
const name = 'Flavio'
```

You can determine the length of a string using the `length` property of it:

```js
'Flavio'.length //6
const name = 'Flavio'
name.length //6
```

This is an empty string: `''`. Its length property is 0:

```js
''.length //0
```

Two strings can be joined using the `+` operator:

```js
"A " + "string"
```

You can use the `+` operator to *interpolate* variables:

```js
const name = 'Flavio'
"My name is " + name //My name is Flavio
```

Another way to define strings is to use template literals, defined inside backticks. They are especially useful to make multiline strings much simpler. With single or double quotes you can't define a multiline string easily - you'd need to use escaping characters.

Once a template literal is opened with the backtick, you just press enter to create a new line, with no special characters, and it's rendered as-is:

```js
const string = `Hey
this

string
is awesome!`
```

Template literals are also great because they provide an easy way to interpolate variables and expressions into strings.

You do so by using the `${...}` syntax:

```js
const var = 'test'
const string = `something ${var}` 
//something test
```

inside the `${}` you can add anything, even expressions:

```js
const string = `something ${1 + 2 + 3}`
const string2 = `something 
  ${foo() ? 'x' : 'y'}`
```