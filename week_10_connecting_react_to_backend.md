# Week 10: Connecting React To The Backend

## Goal

You will understand how React, Express, and MongoDB work together in one full-stack feature.

## Theory

In a full-stack app, each part has a job.

React shows the page and handles user actions.

Express receives requests and sends responses.

MongoDB stores data.

The data flow often looks like this:

```txt
User clicks button
React sends fetch request
Express route receives request
Mongoose talks to MongoDB
Express sends JSON response
React updates the screen
```

## Example

Frontend:

```js
async function loadTasks() {
  const response = await fetch("http://localhost:3000/tasks");
  const data = await response.json();
  setTasks(data);
}
```

Backend:

```js
app.get("/tasks", async (req, res) => {
  const tasks = await Task.find();
  res.json(tasks);
});
```

## Feynman Check

Explain:

- What does React do?
- What does Express do?
- What does MongoDB do?
- What happens after React receives JSON?

## Practice Exercises

### Exercise 1

Write the data flow for loading tasks.

Start with:

```txt
React component appears...
```

End with:

```txt
React displays the tasks.
```

### Exercise 2

Write the data flow for adding a task.

Include:

- form submit
- POST request
- Express route
- MongoDB create
- JSON response
- React state update

### Exercise 3

Look at this JSON response:

```js
[
  { _id: "1", title: "Study full stack", isCompleted: false },
  { _id: "2", title: "Test API", isCompleted: true }
]
```

Write JSX that displays each task title with `.map()`.

## React-Related Exercise

Complete the missing parts:

```jsx
function TasksPage() {
  const [tasks, setTasks] = useState([]);

  async function loadTasks() {
    const response = await fetch("http://localhost:3000/tasks");
    const data = await response.json();
    setTasks(data);
  }

  useEffect(() => {
    loadTasks();
  }, []);

  return (
    <div>
      {tasks.map((task) => (
        <p key={task._id}>{task.title}</p>
      ))}
    </div>
  );
}
```

Answer:

1. Which line sends the request?
2. Which line changes React state?
3. Why does each `<p>` use `key={task._id}`?
4. Which backend route must exist?

## Before-Class Check-In

Be ready to show:

- One full-stack data flow.
- One `fetch()` explanation.
- One React `.map()` example using backend data.

