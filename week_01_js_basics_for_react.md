# Week 1: JavaScript Basics For React

## Goal

You will understand the basic JavaScript values that React components use: variables, strings, numbers, booleans, and simple conditions.

## Theory

A variable stores a value so we can use it later.

Use `const` when the value should not be reassigned. Use `let` when the value may change.

```js
const studentName = "Mina";
let score = 8;
let isPresent = true;
```

### JavaScript Has Types

JavaScript values have types. The ones you will use most:

| Type | Example | Notes |
| --- | --- | --- |
| `string` | `"Mina"` | Text, wrapped in quotes |
| `number` | `8`, `3.14` | No quotes |
| `boolean` | `true`, `false` | Two possible values |
| `undefined` | `undefined` | A variable with no value yet |
| `null` | `null` | An intentional empty value |

`undefined` means "nothing was assigned." `null` means "I am choosing to leave this empty." React will not render `null` or `undefined` as text.

```js
let firstName = "Mina";
let middleName;
let lastName = null;

console.log(firstName);  // "Mina"
console.log(middleName); // undefined
console.log(lastName);   // null
```

### Template Literals

You can build strings with `+` or with backticks and `${}`. Backticks are called template literals.

```js
// String concatenation
const greeting = "Hello, " + studentName;

// Template literal
const greeting2 = `Hello, ${studentName}`;
```

Template literals are easier to read when the string has multiple parts.

```js
const week = 1;
const message = `Week ${week}: JavaScript Basics`;
console.log(message); // "Week 1: JavaScript Basics"
```

### JSX Uses Curly Braces

React uses JavaScript values inside JSX.

```jsx
function Profile() {
  const name = "Mina";

  return <h1>Hello, {name}</h1>;
}
```

The `{name}` part means: "Use the JavaScript value here."

You can also use template literals inside JSX, but most of the time `{name}` is enough.

```jsx
// Both of these work:
<h1>Hello, {name}</h1>
<h1>{`Hello, ${name}`}</h1>

// The first one is shorter and more common.
```

## Example

```js
const courseName = "Web Development 102";
let week = 1;
let isReactWeek = true;

console.log(courseName);
console.log("Week:", week);
console.log("Are we learning React?", isReactWeek);
```

## Feynman Check

Explain these in your own words:

- What is a variable?
- Why do we use `const`?
- What is the difference between `undefined` and `null`?
- What is a template literal?
- Why do we use `{}` inside JSX?

If your explanation sounds complicated, make it shorter.

## Practice Exercises

### Exercise 1

Create these variables:

- `studentName`
- `favoriteWebsite`
- `hoursStudied`
- `isHomeworkDone`

Print each one with `console.log`.

### Exercise 2

Create a variable called `score`.

If the score is 70 or higher, print `"Passed"`.

If the score is below 70, print `"Try again"`.

### Exercise 3

Create two variables:

```js
const firstName = "YourName";
const lastName = "YourLastName";
```

Print a full sentence using a template literal:

```js
const message = `Hello, ${firstName} ${lastName}.`;
console.log(message);
```

### Exercise 4

Create three variables:

```js
let courseName = "Web Development 102";
let week;
let isGraded = null;
```

Print each variable with `console.log`.

Answer: Which one prints `undefined`? Which one prints `null`? Why are they different?

## React-Related Exercise

Read this component:

```jsx
function Welcome() {
  const studentName = "Mina";
  const course = "Web Development 102";

  return (
    <div>
      <h1>Hello, {studentName}</h1>
      <p>Welcome to {course}</p>
    </div>
  );
}
```

Answer:

1. What text appears in the `<h1>`?
2. What text appears in the `<p>`?
3. What happens if `studentName` changes?

Then create your own version with your name and one course goal.

## Before-Class Check-In

Be ready to show:

- Four variables you created.
- One `if` statement.
- One template literal.
- A simple explanation of `{}` in JSX.

