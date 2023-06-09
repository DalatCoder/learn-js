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

## JS fundamentals - Part 2

### Strict mode

Strict mode is a special mode in JS to help us write more
secure code easily.

```js
// first line of code
'use strict'

// other codes
```

### Functions

A function is simply a piece of code that we can reuse over and over again in our code.

So it's a bit like a variable but for whole chunk of code.

```js
function fn() {
  // function body
}

// invoking the function
fn()
```

Functions can accept one or more input parameters

```js
function fn(name) {
  //
}

fn('Hieu')
```

### Function declarations vs. Expressions

In JS, there is different ways of writing functions. And
each type of function works in a slightly
different way.

Function declaration, we use the `function` keyword to declare new function

```js
function fn(params) {
  // body
}
```

Function expression, we define a function and assign it
to a variable. In JS, function is just a value.

```js
const fn = function (params) {
  // body
}
```

We can call the function before it define by using `function declaration`

```js
fn() 

function fn() {

}
```

Personally, I prefer to use function expressions because
this then forces me into a nice structure where I have to
define all the functions before I can use them. I also
like to have everything stored in variables, so both
values and functions.

### Arrow functions

An arrow function is simply a special form of function
expression that is shorter and faster to write.

```js
const fn = () => ''
const fn = (params) => params
```

### Functions calling other functions

```js
const fn1 = () => 1
const fn2 = () => 2

const fn3 = () => fn1() + fn2()
```

### Reviewing functions

3 type of functions in JS. Three different ways of writing functions, but they all work in a similar way: receive `input` data, `transform` data, and then `output`
data.

![Image](assets/functiontypes.png)

The anatomy of a function

![Image](assets/functionanatomy.png)

### Introduction to Array

Array is a `data structure`. We can create an array by using:

- Array literal: `[]`
- Array function: `new Array()`

```js
const friends = ['Michael', 'Steven', 'Peter']
const years = new Array(1991, 1984, 2008)
```

To get element from the array, we use `[]`

```js
const f = friends[0] // the first element
const f2 = friends[1] // the second element

const fn = friends[friends.length - 1] // the last element
```

Change the element inside the array, we can `mutate` the
element inside the array

```js
friends[1] = 'John'
```

### Basic array operations

JS has some built-in functions that we can basically apply
directly on arrays. And these are called methods and we
can think of methods as array operations basically.

Add new element to the array

```js
const friends = ['Michael']

// end
friends.push('John')

// start
friends.unshift('Peter')
```

Remove element from the array

```js
// remove the last element
const e = friends.pop()

// remove the first element
const f = friends.shift()
```

Get index of a element

```js
const i = friends.index('Steven')
```

Check if the element contains inside the array

```js
friends.include('John') // true
friends.include('Ariel') // false
```

### Introduction to Objects

Object is a `data structure` in JS.

Object contains `key-value` pairs

```js
const jonas = {
  firstName: 'Jonas',
  lastName: 'Schmedmann'
}
```

Objects are probably the most fundamental concept in the
whole of JS language. So there are many ways of creating
objects.

- Object literal syntax: `{}`

### Dot vs. Bracket notation

The order of properties inside the object is not matter.

The are 2 ways to get value of a property:

- Using dot (`.`) operator: `jonas.firstName`
- Using bracket notation (`[]`): `jonas['firstName']`.
  Inside the `[]`, we can put anything that produce a value (`expressions`)

`undefined` is what we get when try to access a property
on an object that does not exist.

### Object methods

We can add functions to an object, an all these functions
are called `methods`

```js
const jonas = {
  hello: function() {
    return 'Hello'
  }
}
```

## Developer skills & Editor setup

### Setting up Prettier and VSCode

- Code editor: VSCode
- Formatter: Prettier extension for VSCode

Configure Prettier:

- Create file named `.prettierrc`
- `singleQuote: true`
- `arrowParens: "avoid`

### Installing nodejs and setting up a dev environment

We can install a development tool called `live-server` to
automatically reload the web browser when the source code changed.

- Install NodeJS: `node -v`
- Install `live-server` package: `npm install live-server -g`
- Type command `live-server` in the terminal

### Learning how to code

How to `fail`:

- He didn't have a clear goal at the beginning of his journey
- He started by watching courses and reading tutorials, but he would just copy the code without caring how it works. Sometimes he would just copy and paste code
- He didn't reinforce what he was learning by doing small challenges or taking notes
- He didn't practice coding, and didn't come up with his own project ideas
- He quickly became frustrated when his code was not perfectly clean or efficient

### How to think like a developer: become a problem solver

Solving problem is one of the most important things in programming. So if your goal is to become a greate programmer, you need to learn how to deal with problems effectively.

Fail:

- He jumps at the problem without much thinking
- He implements his solution in an unstructured way
- He gets stressed out when things don't work
- He is too proud to research solutions

Fix:

- Stay calm and slow down, don't just jump at a problem without a plan
- Take a very logical and rational approach (programming is just logic, in the end...)
- Use `4-step` framework to solve any problem

Step 1: Make sure you 100% understand the problem. Ask the right questions to get a clear picture of the problem

Step 2: Divide and conquer: break a big problem into smaller sub-problems

Step 3: Don't be afraid to do as much research as you have to

Step 4: For bigger problems, write pseudo-code before writing the actual code

### Using Google, StackOverflow and MDN

### Debugging (Fixing errors)

> Find and fix errors

Software bug: defect or problem in a computer program. Basically, any unexpected or uninteded behavior of a computer program is a software bug.

Bugs are completely normal in software development

Identify bug (becoming aware that there is a bug):

- During development
- Testing software
- User reports during production
- Context: browsers, users, etc.

Find (Isolating where exactly the bug is happening in code)

- Developer console (simple code)
- Debugger (complex code)

Fix (correct the bug)

- Replace wrong solution with new correct solution

Prevent (preventing it from happening again)

- Searching for the same bug in similar code
- Writing test using testing software

### Debugging with the console and breakpoints

Set breakpoints

- Open developer console
- Go to `sources` tab
- Set breakpoint and start debugging

Or place the `debugger` inside the source code

### JS in the Browser: DOM and Events fundamentals

#### Project: Guess my number

Initial files at `./01.guess-my-number`

#### What's the DOM and DOM manipulation

What is the DOM?

> DOM: Document Object Model, structured representation of HTML documents,
> allows JS to access HTML elements and styles to manipulate them.

The DOM is the connection point between HTML and JS.

Whatever is in the HTML document also has to be in the DOM. The DOM really is
a complete representation of the HTML document, so that we can manipulate it
in complex ways.

![Image](assets/dom.png)

The DOM, DOM methods and properties for DOM manipulation are not part of
the JS language. They are actually part of something called the `web APIs`.

![Image](assets/domvsjs.png)
