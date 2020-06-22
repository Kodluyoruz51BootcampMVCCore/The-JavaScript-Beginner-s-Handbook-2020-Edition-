# A brief intro to the syntax of JavaScript
In this little introduction I want to tell you about 5 concepts:

* white space

* case sensitivity

* literals

* identifiers

* comments

  

### White space

 JavaScript does not consider white space meaningful. Spaces and line breaks can be added in any fashion you might like, at least in theory.

In practice, you will most likely keep a well defined style and adhere to what people commonly use, and enforce this using a linter or a style tool such as Prettier.

For example, I always use 2 space characters for each indentation.

### Case sensitive
JavaScript is case sensitive. A variable named `something` is different than `Something`.

The same goes for any identifier.

### Literals
We define literal as a value that is written in the source code, for example, a number, a string, a boolean or also more advanced constructs, like Object Literals or Array Literals:

```javascript
5
'Test'
true
['a', 'b']
{color: 'red', shape: 'Rectangle'}

```

### Identifiers
An identifier is a sequence of characters that can be used to identify a variable, a function, or an object. It can start with a letter, the dollar sign $ or an underscore _, and it can contain digits. Using Unicode, a letter can be any allowed character, for example, an emoji 😄.

```javascript
Test
test
TEST
_test
Test1
$test

```
The dollar sign is commonly used to reference DOM elements.

Some names are reserved for JavaScript internal use, and we can't use them as identifiers.

### Comments
Comments are one of the most important parts of any program, in any programming language. They are important because they let us annotate the code and add important information that otherwise would not be available to other people (or ourselves) reading the code.

In JavaScript, we can write a comment on a single line using `//`. Everything after `//` is not considered as code by the JavaScript interpreter.

Like this:

```javascript
// a comment
true //another comment

```
Another type of comment is a multi-line comment. It starts with `/*` and ends with `*/.`

Everything in between is not considered as code:

```javascript
/* some kind
of 
comment 

*/
```
