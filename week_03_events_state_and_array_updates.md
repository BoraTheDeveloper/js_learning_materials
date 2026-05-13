# Week 3: Events, State, And Array Updates

## Goal

You will understand the JavaScript behind React state and user interaction.

## Theory

An event is something the user does.

Examples:

- Click a button.
- Type in an input.
- Submit a form.

In React, an event handler is a function that runs after an event.

```jsx
function handleClick() {
  console.log("Button clicked");
}
```

State stores data that can change on the screen.

```jsx
const [count, setCount] = useState(0);
```

When state changes, React updates the UI.

For arrays, React usually creates a new array instead of changing the old one directly.

```js
const tasks = ["Study JS", "Practice React"];
const newTasks = [...tasks, "Build planner"];
```

The spread syntax `...tasks` copies the old array values into a new array.

### `.map()` Creates a New Array

`.map()` runs a function on every item and returns a new array with the results.

```js
const tasks = ["Study JS", "Practice React"];
const louder = tasks.map((task) => task.toUpperCase());
console.log(louder); // ["STUDY JS", "PRACTICE REACT"]
```

In React, `.map()` is how you turn a list of data into a list of elements.

```jsx
function TaskList({ tasks }) {
  return (
    <div>
      {tasks.map((task) => (
        <p>{task}</p>
      ))}
    </div>
  );
}
```

Each item in the array becomes one `<p>` element.

## Example

```js
let count = 0;

function increaseCount() {
  count = count + 1;
  console.log(count);
}

increaseCount();
increaseCount();
```

React uses the same idea, but with `useState`.

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  function increaseCount() {
    setCount(count + 1);
  }

  return <button onClick={increaseCount}>{count}</button>;
}
```

## Feynman Check

Explain:

- What is an event?
- What is an event handler?
- Why does React use state?
- Why do we create a new array?
- What does `.map()` do? How is it different from a `for` loop?

## Practice Exercises

### Exercise 1

Create a variable called `count`.

Write a function called `increaseCount` that adds 1 to `count`.

Call the function three times.

### Exercise 2

Create an array of tasks.

Use spread syntax to add one new task.

Print the new array.

### Exercise 3

Create this array:

```js
const tasks = [
  { title: "Study JS", isCompleted: false },
  { title: "Practice React", isCompleted: false }
];
```

Create a new array where the first task is completed.

Hint:

```js
const updatedTasks = tasks.map((task, index) => {
  if (index === 0) {
    return { ...task, isCompleted: true };
  }

  return task;
});
```

## React-Related Exercise

Read this code:

```jsx
function TaskList() {
  const [tasks, setTasks] = useState(["Study JS"]);

  function addTask() {
    setTasks([...tasks, "Practice React"]);
  }

  return (
    <div>
      <button onClick={addTask}>Add Task</button>
      {tasks.map((task) => (
        <p>{task}</p>
      ))}
    </div>
  );
}
```

Answer:

1. What happens when the button is clicked?
2. Why does the code use `[...tasks, "Practice React"]`?
3. What does `.map()` do here?

## Before-Class Check-In

Be ready to show:

- One event handler function.
- One array update with spread syntax.
- One explanation of `useState`.

