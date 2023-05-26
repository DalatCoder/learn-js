# The complete JS course 2023: From zero to expert

## Course introduction

- Fundamentals 1 & 2
- Developer skills
- DOM manipulation
- How JS works
- Modern operators (ES6+)
- Functions
- Arrays
- Numbers, dates, timers
- Advanced DOM
- Object oriented JS
- Mapty project
- Asynchronous JS
- Modern JS applications
- Forkify project
- Deployment and git

[Course source code on Github](https://github.com/jonasschmedtmann/complete-javascript-course)

Some quick considerations before we start:

- This course is for all of you!
- You need to code along with me
- Try all the coding challenges, don't beat yourself up if you
  can't figure it out!
- If you want the course material to stick, take notes
- Before moving on from a section, make sure that you understand
  exactly what was coverred
- Most importantly, have fun!

Setting up our code editor:

- VSCode
- Autosave: onFocusChange (close window, change tab)

## JS fundamentals - Part 1

### Hello world

Try code in the browser developer tool

```js
alert("Hello World!")

let js = 'amazing'
if (js === 'amazing') alert('JavaScript is FUN!')

js = 'boring'
if (js === 'amazing') alert('JavaScript is FUN!')
```

### Brief introduction to JS

> JavaScript is a high-level, object-oriented, multi-paradigm programming language

- A programming language is basically just a tool that allows us
  to write code that will instruct a computer to do something
- High-level: we don't have to worry about complex stuff like memory management,... It make the language a lot easier to write and to learn
- OOP: the language is mostly based on the concept of objects for storing most kinds of data
- Multi-paradigm language: we can use all kinds of different programming styles, such as imperative and declarative programming

The role of JavaScript in web development:

- 3 core technologies of the web: HTML, CSS, JS
  - HTML: content
  - CSS: presentation
  - JS: building web applications

There is nothing you can't do with JS (almost)

- Dynamic effects and web application in the browser (front-end apps)
- FE web framework: React, Angular, Vue
- Web applications on web servers (back-end apps)
- Native mobile applications: React native, ionic
- Native desktop applicatioins: electron

JavaScript releases

- ES5
- ES6/ES2015 (biggest update to the language ever)
- ES7/ES2016
- ...
- New updates to JS every single year

### Linking a JS file

In the browser, all JS code need to be attached to an HTML
file

- Using inline script

```html
<script>
  console.log('Hello Wolrd')
</script>
```

- Using external JS file

```html
<script src='script.js'></script>
```

### Values and Variables

A value is basically a piece of data, it's the most fundamental unit of information that we have in programming

```js
console.log('Jonas')
console.log(23)
```

Now, one extremely useful thing that we can do with value
is to store them into variable, and so this way we can reuse them over and over again.

Explain the code below:

- We declare a variable named `firstName`
- We assign the value of `Jonas` to this variable
- We reassign the value of `John` to the variable

```js
let firstName = 'Jonas'
console.log(firstName)

firstName = 'John'
console.log(firstName)
```

- Using `camelCase` to name variable in JS
- Using `UPPERCASE` to name constant value: `const PI = 3.14`

### Data types

Value can be:

- Object
- Primitive (everything else)

The 7 primitive data types:

- Number: floating point numbers, used for decimals and integers
- String: sequnce of characters, used for text
- Boolean: logical type that can only be `true` or `false`, used for taking decisions
- Undefined: value taken by a variable that is not yet defined (empty value)
- Null: also means 'empty value'
- Symbol: value that is unique and cannot be changed (not useful for now)
- Big int: larger integers than the `Number` type can hold

> JavaScript has dynamic typing: we do not have to manually define
> the data type of the value stored in a variable. Instead, data types
> are determined automatically

Value has type, NOT variable!

Using `typeof` operator to get the `type` of the value

- `typeof null`: object (legacy bug in JS)
- `typeof undefined`: undefined

### Declaring variables

- `let`: declare variables that can be changed later (`reassign` new value to the variable, or `mutate` the variable)
- `const`: declare variables that are not supposed to change (`immutable`)

As a best pratice for writing clean code, I always recommend to use `const` by default and `let` only when you are really sure that the variable needs to change at some point in the future.

It's a good practice to have as little variable `mutations` as possible because changing variable introduces a potential to create bugs.

- `var` is the old way to declare new variables
- We can declare the variable without using the `let`, `const` or `var` keyword, the variable will be placed at the property of the global object (`window` object)

### Basic operators

An operator basically allows us to transform values or combine multiple values are really do all kinds of work with values.

There are many categories of operators:

- Mathematical operators: +, -, *, /, **
- Concatenate strings: +
- Comparison operators: >, <, ==, ===
- Logical operators: &&, ||, !
- Assignment operators: =, +=, -=, ++, --,...
- ...

### Operator precedence

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence)

### Strings and template literals

To concatenate strings, we use the `+` operator.

We can use the backtick character ``` to build string easier

```js
const name = 'Hieu'
const greeting = `Hello ${name}`

console.log(greeting)
```

### Taking decisiions

- `if(condition)`: condition is being `boolean` value

```js
if (true) {
  console.log(true)
} else {
  console.log(false)
}
```

We take decisions with code all the time which is essentially what we did here so that we can execute certain parts of our program based on certain condition

`if-else` block is called `control structure`. And it is called a control structure because this structure actually allows us to have more control over the way that our code is executed

### Type conversion and coercion

- `type conversion` is when we manually convert from one type to another.
- `type coercion` is when JS automatically converts type behind the scenes for us.

Convert string to number:

- `Number('1')`: `1`
- `Number('a')`: `NaN`

Convert number to string:

- `String(1)`

### Truthy and falsy values

- `falsy` values are values that are not exactly `false`, but will become `false` when we try to convert them into a `boolean`. There are only `5` falsy values in JS:
  - `0`
  - `''`
  - `undefined`
  - `null`
  - `NaN`

- Everything else are so-called `truthy` values.

```js
console.log(Boolean(0))
console.log(Boolean(undefined))
console.log(Boolean(null))
console.log(Boolean(NaN))
console.log(Boolean(''))
```

### Equality operators: `==` vs. `===`

- `===`: strict equality operator, it does not perform `type coercion`
- `==`: loose equality operator, it perform `type coercion`

> Avoid using the `==` as much as you can

### Boolean logic

Boolean logic is a branch of computer science, which uses `true` and `false` values to solve complex logical problems

The `true` table

`and` operator: `true` when ALL are `true`

- `true` and `true`: true
- `true` and `false`: false
- `false` and `true`: false
- `false` and `false`: false

`or` operator: `true` when ONE is `true`

- `true` and `true`: true
- `true` and `false`: true
- `false` and `true`: true
- `false` and `false`: false

`not` operator: inverts `true/false` value

### The `switch` statement

An alternative way of writing a complicated `if/else` statement

```js
const day = 'monday'

switch(day) {
  case 'monday':
    console.log('Plan course structure')
    console.log('Go to coding meetup')
    break
  case 'tuesday':
    console.log('Preprare theory videos')
    break
  case 'wednesday':
  case 'thursday':
    console.log('Write code examples')
    break
  case 'friday':
    console.log('Record videos')
    break
  case 'saturday':
  case 'sunday':
    console.log('Enjoy the weekend')
    break
  default:
    console.log('Not a valid day')
}
```

### Statements and Expressions

- An `expression` is a piece of code that produces a `value`
  - `4 + 4`
  - `2000`
  - `true && false && !false`

- `statement` is like a bigger piece of code that is executed and which does not produce a value on itself

Now, basically we write our whole programs as a sequence of actions. And these actions are statements.

### The conditional (ternary) operator

The conditional operator allows us to write something similar to an `if/else` statement but all in one line.

`condition ? true : false`

### JavaScript releases: ES5, ES6+ and ESNext

Backwards compatibility: don't break the web

- Old features are `never` removed
- Not really new versions, just incremental updates (releases)
- Websites keep working `forever`!

There are not forwards compatible in JS, so how to use modern JS today? Because browsers that users are using might be old and there's no forwards compatibility.

- During development: simply use the latest Google Chrome!
- During production: use `babel` to transpile and polyfill your code(converting back to ES5 to ensure browser compatibility for all users)
