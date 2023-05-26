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
