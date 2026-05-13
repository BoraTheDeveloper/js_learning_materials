# Week 2: Functions, Arrays, Objects, And Props

## Goal

You will understand the JavaScript ideas behind React components and props.

## Theory

A function is a reusable action.

```js
function greet(name) {
  return "Hello, " + name;
}
```

An arrow function is a shorter function style.

```js
const greet = (name) => {
  return "Hello, " + name;
};
```

React components are functions that return UI.

```jsx
function Card() {
  return <div>Card content</div>;
}
```

An array stores a list.

```js
const tasks = ["Study JS", "Build component", "Review props"];
```

An object stores related details.

```js
const student = {
  name: "Mina",
  course: "Web Development 102",
  isActive: true
};
```

Props are values passed into a component.

```jsx
function StudentCard(props) {
  return <h2>{props.name}</h2>;
}
```

### Destructuring

Destructuring lets you pull values out of an object or array into individual variables.

```js
// Without destructuring
const student = { name: "Mina", course: "WD 102" };
const name = student.name;
const course = student.course;

// With destructuring
const { name, course } = student;
```

Both do the same thing. Destructuring is shorter.

Destructuring also works with function parameters.

```js
function describeStudent({ name, course }) {
  return `${name} is taking ${course}.`;
}

console.log(describeStudent(student));
```

You will see destructuring everywhere in React:

```jsx
// Destructuring props
function StudentCard({ name, course }) {
  return (
    <div>
      <h2>{name}</h2>
      <p>{course}</p>
    </div>
  );
}
```

## Example

```js
const student = {
  name: "Mina",
  goal: "Understand React props"
};

function describeStudent(person) {
  return person.name + " wants to " + person.goal + ".";
}

console.log(describeStudent(student));
```

## Feynman Check

Explain these ideas simply:

- A function is like...
- An array is like...
- An object is like...
- Destructuring is like...
- Props are like...

Use real-life examples, not technical words only.

## Practice Exercises

### Exercise 1

Write a function called `sayHello`.

It should take a name and return:

```txt
Hello, name
```

### Exercise 2

Create an array of three course topics.

Print the first topic.

Print the last topic.

### Exercise 3

Create an object called `task`.

It should have:

- `title`
- `isCompleted`
- `week`

Print each property.

### Exercise 4

Create an array of task objects.

Each task should have:

- `title`
- `isCompleted`

Print the title of each task.

### Exercise 5

Create this object:

```js
const student = {
  name: "Dara",
  course: "WD 102",
  week: 4
};
```

Use destructuring to pull out `name` and `course` into separate variables.

Print them.

## React-Related Exercise

Read this component:

```jsx
function CourseCard({ title, description }) {
  return (
    <div>
      <h2>{title}</h2>
      <p>{description}</p>
    </div>
  );
}
```

Answer:

1. What props does `CourseCard` need?
2. What happens if `title` is missing?
3. Why does this component use `{ title, description }` instead of `props`?
4. Why is this component reusable?

Then write your own `TaskCard` component idea. It should show a task title and whether it is complete.

## Before-Class Check-In

Be ready to show:

- One function.
- One array.
- One object.
- One destructuring example.
- A simple explanation of props.

