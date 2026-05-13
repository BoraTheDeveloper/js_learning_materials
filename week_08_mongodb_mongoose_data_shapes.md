# Week 8: MongoDB And Mongoose Data Shapes

## Goal

You will understand records, schemas, and models before using MongoDB with Express.

## Theory

MongoDB stores data as documents.

A document looks like a JavaScript object.

```js
{
  title: "Study MongoDB",
  isCompleted: false
}
```

Mongoose helps JavaScript work with MongoDB.

A schema describes the shape of the data.

```js
const taskSchema = new mongoose.Schema({
  title: String,
  isCompleted: Boolean
});
```

A model lets us create, find, update, and delete documents.

```js
const Task = mongoose.model("Task", taskSchema);
```

## Example

```js
const task = {
  title: "Create Task schema",
  isCompleted: false,
  createdAt: "2026-05-12"
};

console.log(task.title);
```

## Feynman Check

Explain:

- What is a document?
- What is a schema?
- What is a model?
- Why should data have a clear shape?

## Practice Exercises

### Exercise 1

Design a task object with these fields:

- `title`
- `description`
- `isCompleted`
- `priority`

### Exercise 2

Design a student object with these fields:

- `name`
- `email`
- `course`
- `isActive`

### Exercise 3

For each field below, choose a type:

- `title`
- `age`
- `isCompleted`
- `tags`

Use these types:

- String
- Number
- Boolean
- Array

## React-Related Exercise

React receives this task from the backend:

```js
const task = {
  _id: "abc123",
  title: "Study schemas",
  isCompleted: false
};
```

Answer:

1. Which value should React display as the task title?
2. Which value can React use when updating or deleting the task?
3. Why does the backend include `_id`?

## Before-Class Check-In

Be ready to show:

- One task data shape.
- One student data shape.
- A simple explanation of schema and model.

