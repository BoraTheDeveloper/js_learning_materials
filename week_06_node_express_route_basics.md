# Week 6: Node And Express Route Basics

## Goal

You will understand how JavaScript runs on the backend with Node.js and Express.

## Theory

Node.js lets JavaScript run outside the browser.

Express helps us build a backend server.

A route tells the server how to respond to a request.

```js
app.get("/tasks", (req, res) => {
  res.json([{ title: "Study Express" }]);
});
```

Read this as:

When someone visits `/tasks` with a GET request, send back JSON data.

`req` means request. It contains information from the client.

`res` means response. It sends information back to the client.

## Example

```js
const tasks = [
  { id: 1, title: "Study Express", isCompleted: false },
  { id: 2, title: "Build route", isCompleted: false }
];

app.get("/tasks", (req, res) => {
  res.json(tasks);
});
```

## Feynman Check

Explain:

- What does Node.js do?
- What does Express help us build?
- What is a route?
- What is the difference between `req` and `res`?

## Practice Exercises

### Exercise 1

Create an array called `tasks`.

Each task should have:

- `id`
- `title`
- `isCompleted`

### Exercise 2

Write a route idea in plain English:

```txt
GET /students should return...
```

Then write the matching Express route.

### Exercise 3

Create this route:

```txt
GET /health
```

It should return:

```json
{ "status": "ok" }
```

## React-Related Exercise

Imagine React runs this code:

```js
const response = await fetch("http://localhost:3000/tasks");
const data = await response.json();
```

Answer:

1. Which Express route should receive this request?
2. What should the backend send back?
3. Why should the backend send JSON?

## Before-Class Check-In

Be ready to show:

- One Express route.
- One explanation of `req`.
- One explanation of `res`.

