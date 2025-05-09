# MWAD-EX_03-To-Do-List-using-JavaScript
## Date: 09.05.2025

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
to.html
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Todo List Manager</title>
  <link rel="stylesheet" href="to.css" />
</head>
<body>
  <main class="container" role="main">
    <h1>Todo List</h1>

    <form id="todo-form" class="input-group" autocomplete="off">
      <label for="todo-input" class="visually-hidden"><h3>Enter a new task</h3></label>
      <input
        type="text"
        id="todo-input"
        name="todo"
        placeholder="Add a task..."
        aria-label="Todo text"
        required
      />
      <button type="submit" id="add-btn" aria-label="Add todo">Add</button>
    </form>

    <section aria-live="polite">
      <ul id="todo-list" aria-label="List of todos"></ul>
    </section>
  </main>

  <script src="to.js"></script>
</body>
</html>
```
to.css
```
/* Reset some defaults */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(to right, #ffffff, #4c525b);
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  background-color: #000000;
  padding: 30px;
  border-radius: 16px;
  max-width: 500px;
  width: 100%;
  box-shadow: 0 8px 16px rgb(0, 0, 0);
}

h1 {
  text-align: center;
  margin-bottom: 24px;
  color: #ffffff;
  font-size: 28px;
}

h3 {
  text-align: center;
  margin-bottom: 24px;
  color: #fffefe;
  font-size: 28px;
}

.input-group {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

input[type="text"] {
  flex-grow: 1;
  padding: 12px 16px;
  border: 1px solid #ccc;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.3s;
}

input[type="text"]:focus {
  border-color: #f67d3b;
  outline: none;
}

button {
  padding: 12px 18px;
  background-color: #f67d3b;
  color: rgb(0, 0, 0);
  border: none;
  border-radius: 8px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #eb7b25;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #fffafa;
  margin-bottom: 12px;
  padding: 12px 16px;
  border-radius: 8px;
  box-shadow: 0 1px 4px rgba(255, 255, 255, 0.871);
  transition: transform 0.2s;
}

li:hover {
  transform: translateY(-2px);
}

li.completed span {
  text-decoration: line-through;
  color: #fbf0f0;
}

li span {
  flex-grow: 1;
  cursor: pointer;
  font-size: 16px;
  color: #000000;
}

li button {
  background: none;
  border: none;
  color: #ef4444;
  font-weight: bold;
  font-size: 14px;
  cursor: pointer;
  transition: color 0.3s;
}

li button:hover {
  color: #dc2626;
}

@media (max-width: 500px) {
  .container {
    padding: 20px;
  }

  input[type="text"],
  button {
    font-size: 14px;
    padding: 10px;
  }
}
```
to.js
```
let todos = [];

const todoInput = document.getElementById('todo-input');
const addBtn = document.getElementById('add-btn');
const todoList = document.getElementById('todo-list');

function renderTodos() {
  todoList.innerHTML = '';
  todos.forEach(todo => {
    const li = document.createElement('li');
    li.className = todo.completed ? 'completed' : '';
    
    const span = document.createElement('span');
    span.textContent = todo.text;
    span.onclick = () => toggleTodo(todo.id);

    const deleteBtn = document.createElement('button');
    deleteBtn.textContent = 'Delete';
    deleteBtn.onclick = () => deleteTodo(todo.id);

    li.appendChild(span);
    li.appendChild(deleteBtn);
    todoList.appendChild(li);
  });
}

function addTodo(text) {
  todos.push({
    id: Date.now(),
    text,
    completed: false
  });
  renderTodos();
}

function toggleTodo(id) {
  todos = todos.map(todo =>
    todo.id === id ? { ...todo, completed: !todo.completed } : todo
  );
  renderTodos();
}

function deleteTodo(id) {
  todos = todos.filter(todo => todo.id !== id);
  renderTodos();
}

addBtn.addEventListener('click', () => {
  const text = todoInput.value.trim();
  if (text !== '') {
    addTodo(text);
    todoInput.value = '';
  }
});
```
## OUTPUT
![Screenshot 2025-05-06 203406](https://github.com/user-attachments/assets/358fc461-7f14-49a6-82c4-500cd2d2e289)
![Screenshot 2025-05-06 204925](https://github.com/user-attachments/assets/5ced89ed-01f0-4ee4-a5ea-f1655d7c4ff4)
![Screenshot 2025-05-06 204941](https://github.com/user-attachments/assets/624b0a5f-c123-46d2-a53a-e36529fd238f)


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
