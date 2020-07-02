# 3.1.3 - fetch()

---

- `fetch()` is a JavaScript (but not NodeJS) Promise-based function.
- It's mainly used to
  - `GET` from somewhere
  - `POST` data somewhere

The syntax is very similar to Promises.

---

For now, we will follow this template for our communications with the server.

```js
// NOT TO BE WRITTEN IN NODE, ONLY IN JAVASCRIPT.
fetch("<SERVER_ENDPOINT_URL>")
  .then((res) => res.json()) // convert the response to json
  .then((data) => {
    // do something with the data from the server
    console.log(data);
  });
```

We will talk more about this in a later lecture, but for now this will suit our purposes.

---

## JSON (or JavaScript Object Notation)

- It is a minimal, readable format for structuring data.
- It is mainly used to transmit data between servers and web applications.
- It looks ALOT like a JS Object, and can be accessed using `dot` notation.

---

### Example

```json
{
  "name": "Peter",
  "alterego": "Spider-man",
  "villainsDefeated": 303,
  "car": null,
  "friends": ["Mary Jane", "Gwen", "Miles"]
}
```

---

To keep things clean and simple,

- the frontend will always expect `json` from the server (backend).
- the backend will always send data as a `json`.

---

```js
// frontend
fetch("/cat-message")
  .then((res) => res.json())
  .then((data) => {
    console.log(data);
  });
```

```js
// backend
.get('/', (req, res) => {
  res.status(200).json({ status: 200, message: "This is the homepage... it's empty :(" });
})
```

---

_Let's create a server!_
