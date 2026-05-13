# Week 5: Fetch, JSON, And Async JavaScript

## Goal

You will understand how React asks an API for data and displays the result.

## Theory

An API is a way for one program to ask another program for data.

Most web APIs return JSON.

JSON looks like JavaScript objects and arrays.

```json
{
  "title": "Study fetch",
  "isCompleted": false
}
```

`fetch()` sends a request.

```js
fetch("https://example.com/tasks");
```

API requests take time, so JavaScript uses promises and async code.

### Promises

A promise is like a delivery ticket. You order something, get a ticket back, and the item arrives later.

```js
const promise = fetch("https://example.com/tasks");
// promise is not the data yet — it is a promise that data is coming
```

A promise can succeed (resolve) or fail (reject). We usually skip the raw promise syntax and use `async`/`await` instead, which is easier to read.

### `async` and `await`

`async` goes before a function. `await` pauses inside that function until the promise finishes.

```js
async function loadTasks() {
  const response = await fetch("https://example.com/tasks");
  const data = await response.json();
  console.log(data);
}
```

Read line by line:

1. `await fetch(...)` — send the request, wait for the response.
2. `await response.json()` — read the response body as JSON, wait for it to finish.
3. `console.log(data)` — now `data` has the actual result.

In React, `useEffect` can load data when the component first appears.

## Example

```js
async function loadUser() {
  const response = await fetch("https://jsonplaceholder.typicode.com/users/1");
  const user = await response.json();

  console.log(user.name);
}

loadUser();
```

## Feynman Check

Explain:

- What is an API?
- What is JSON?
- What is a promise? Use a real-life analogy.
- Why do we use `await`?
- What does `response.json()` do?

## Practice Exercises

### Exercise 1

Look at this JSON:

```js
const task = {
  title: "Practice fetch",
  isCompleted: false
};
```

Print the task title.

### Exercise 2

Look at this array:

```js
const users = [
  { name: "Mina", email: "mina@example.com" },
  { name: "Dara", email: "dara@example.com" }
];
```

Use `.map()` to print each user's name.

### Exercise 3

Write an async function called `loadPosts`.

Use this URL:

```txt
https://jsonplaceholder.typicode.com/posts
```

Print the first post title.

### Exercise 4

Answer these in your own words:

1. What is a promise? Use a real-life analogy.
2. What does `await` do?
3. What happens if you forget `await` before `fetch()`?

## React-Related Exercise

Read this code:

```jsx
function UsersPage() {
  const [users, setUsers] = useState([]);
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    async function loadUsers() {
      const response = await fetch("https://jsonplaceholder.typicode.com/users");
      const data = await response.json();

      setUsers(data);
      setIsLoading(false);
    }

    loadUsers();
  }, []);

  if (isLoading) {
    return <p>Loading...</p>;
  }

  return (
    <div>
      {users.map((user) => (
        <p>{user.name}</p>
      ))}
    </div>
  );
}
```

Answer:

1. What data starts as an empty array?
2. What changes `isLoading` to `false`?
3. Why does the component use `.map()`?
4. What does the empty `[]` at the end of `useEffect` mean?

## Before-Class Check-In

Be ready to show:

- One JSON object explanation.
- One `fetch()` example.
- One promise explanation.
- One explanation of loading state.

