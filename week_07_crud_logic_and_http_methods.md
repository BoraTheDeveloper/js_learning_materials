# Week 7: CRUD Logic And HTTP Methods

## Goal

You will understand GET, POST, PUT, and DELETE before using them in Express routes.

## Theory

CRUD means:

- Create
- Read
- Update
- Delete

HTTP methods often match CRUD actions.

| Action | HTTP Method | Example Route |
| --- | --- | --- |
| Read all tasks | GET | `/tasks` |
| Create a task | POST | `/tasks` |
| Update a task | PUT | `/tasks/:id` |
| Delete a task | DELETE | `/tasks/:id` |

The `:id` part means the route uses a changing value.

```txt
/tasks/1
/tasks/2
/tasks/3
```

## Example

```js
let tasks = [
  { id: 1, title: "Study CRUD", isCompleted: false }
];

function createTask(title) {
  const newTask = {
    id: Date.now(),
    title: title,
    isCompleted: false
  };

  tasks.push(newTask);
  return newTask;
}
```

## Feynman Check

Explain:

- What does CRUD mean?
- Which method reads data?
- Which method creates data?
- Why do update and delete routes need an ID?

## Practice Exercises

### Exercise 1

Create an array of three task objects.

Each task needs:

- `id`
- `title`
- `isCompleted`

### Exercise 2

Write a function called `findTaskById`.

It should take an ID and return the matching task.

Hint: use `.find()`.

### Exercise 3

Write a function called `deleteTaskById`.

It should take an ID and return a new array without that task.

Hint: use `.filter()`.

### Exercise 4

Write a function called `toggleTask`.

It should switch a task from incomplete to complete.

Hint: use `.map()`.

## React-Related Exercise

Read this frontend idea:

```js
async function deleteTask(id) {
  await fetch(`http://localhost:3000/tasks/${id}`, {
    method: "DELETE"
  });
}
```

Answer:

1. Which backend route should match this request?
2. Why does the URL include the task ID?
3. What should the frontend do after delete succeeds?

## Before-Class Check-In

Be ready to show:

- One `.find()` example.
- One `.filter()` example.
- One `.map()` update example.
- A simple explanation of CRUD.

