HTML

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Dev To-Do App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Web Dev To-Do App</h1>
        <div class="task-form">
            <input type="text" id="taskInput" placeholder="Add a task...">
            <button onclick="addTask()">Add</button>
        </div>
        <ul id="taskList"></ul>
    </div>

    <script src="script.js"></script>
</body>
</html>

  CSS

  /* styles.css */
body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.container {
    background-color: white;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    text-align: center;
}

h1 {
    margin-bottom: 20px;
}

.task-form {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 20px;
}

input[type="text"] {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 3px;
    flex-grow: 1;
    margin-right: 10px;
}

button {
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 3px;
    padding: 10px 20px;
    cursor: pointer;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 10px 0;
    padding: 10px;
    background-color: #eee;
    border-radius: 3px;
}

JAVASCRIPT

// script.js
const taskInput = document.getElementById("taskInput");
const taskList = document.getElementById("taskList");

function addTask() {
    const taskText = taskInput.value.trim();
    if (taskText === "") return;

    const listItem = document.createElement("li");
    listItem.innerHTML = `
        <span>${taskText}</span>
        <button onclick="deleteTask(this)">Delete</button>
    `;

    taskList.appendChild(listItem);
    taskInput.value = "";
}

function deleteTask(button) {
    const listItem = button.parentElement;
    taskList.removeChild(listItem);
}

