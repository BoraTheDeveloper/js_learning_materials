# Week 4: Forms And Controlled Inputs

## Goal

You will understand input values, form submission, and controlled components in React.

## Theory

A form collects information from the user.

In plain HTML, a form can refresh the page when submitted. In React, we often stop that refresh with `preventDefault()`.

```js
function handleSubmit(event) {
  event.preventDefault();
}
```

A controlled input is an input where React state controls the value.

```jsx
const [title, setTitle] = useState("");

<input
  value={title}
  onChange={(event) => setTitle(event.target.value)}
/>;
```

The input shows `title`. When the user types, `setTitle` updates `title`.

## Example

```js
let taskTitle = "";

function updateTaskTitle(newValue) {
  taskTitle = newValue;
  console.log(taskTitle);
}

updateTaskTitle("Study forms");
```

React uses the same idea, but the input and state stay connected.

## Feynman Check

Explain:

- What does a form do?
- What does `event.preventDefault()` prevent?
- What does `event.target.value` mean?
- What makes an input controlled?

## Practice Exercises

### Exercise 1

Create a variable called `taskTitle`.

Write a function that changes `taskTitle` to a new value.

Print the result.

### Exercise 2

Write a function called `isEmpty`.

It should return `true` if a string is empty.

It should return `false` if the string has text.

### Exercise 3

Create an array called `tasks`.

Write a function called `addTask`.

If the new task title is empty, print:

```txt
Task title is required.
```

If the title has text, add it to the task array.

## React-Related Exercise

Read this code:

```jsx
function TaskForm() {
  const [title, setTitle] = useState("");
  const [tasks, setTasks] = useState([]);

  function handleSubmit(event) {
    event.preventDefault();

    if (title === "") {
      return;
    }

    setTasks([...tasks, title]);
    setTitle("");
  }

  return (
    <form onSubmit={handleSubmit}>
      <input
        value={title}
        onChange={(event) => setTitle(event.target.value)}
      />
      <button>Add Task</button>
    </form>
  );
}
```

Answer:

1. Where is the input value stored?
2. What happens when the user types?
3. What happens when the form submits?
4. Why does the code call `setTitle("")`?

## Before-Class Check-In

Be ready to show:

- One input value explanation.
- One validation function.
- One explanation of controlled inputs.

