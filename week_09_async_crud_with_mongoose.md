# Week 9: Async CRUD With Mongoose

## Goal

You will understand the JavaScript pattern used in Express routes that talk to MongoDB.

## Theory

Database work takes time, so Mongoose code usually uses `async` and `await`.

```js
const tasks = await Task.find();
```

CRUD with Mongoose often looks like this:

```js
await Task.create(...)
await Task.find()
await Task.findByIdAndUpdate(...)
await Task.findByIdAndDelete(...)
```

Because database code can fail, route handlers often use `try/catch`.

```js
try {
  const tasks = await Task.find();
  res.json(tasks);
} catch (error) {
  res.status(500).json({ message: "Server error" });
}
```

## Example

```js
app.get("/tasks", async (req, res) => {
  try {
    const tasks = await Task.find();
    res.json(tasks);
  } catch (error) {
    res.status(500).json({ message: "Could not load tasks" });
  }
});
```

## Feynman Check

Explain:

- Why does database code use `await`?
- What does `try` do?
- What does `catch` do?
- What should the server send if something fails?

## Practice Exercises

### Exercise 1

Read this code:

```js
const task = await Task.create({
  title: "Practice Mongoose",
  isCompleted: false
});
```

Answer:

1. What is being created?
2. What fields does the new document have?
3. Why do we use `await`?

### Exercise 2

Write the plain-English meaning of this line:

```js
const deletedTask = await Task.findByIdAndDelete(req.params.id);
```

### Exercise 3

Write a `try/catch` block that sends:

```json
{ "message": "Something went wrong" }
```

when an error happens.

## React-Related Exercise

React sends this request:

```js
await fetch(`http://localhost:3000/tasks/${id}`, {
  method: "PUT",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({ isCompleted: true })
});
```

Answer:

1. Which backend route should receive this request?
2. Where does the backend find the ID?
3. Where does the backend find `isCompleted`?
4. Which Mongoose method could update the document?

## Before-Class Check-In

Be ready to show:

- One async route explanation.
- One `try/catch` explanation.
- One Mongoose CRUD method and what it does.

