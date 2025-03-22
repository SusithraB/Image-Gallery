# Ex03 To-Do List using JavaScript
## Date:18-03-2025

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
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>To-Do List</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background: #f4f4f4;
        text-align: center;
      }

      .container {
        max-width: 400px;
        margin: 50px auto;
        padding: 20px;
        background: white;
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        border-radius: 10px;
      }

      h1 {
        color: #333;
      }

      .todo-input {
        display: flex;
        justify-content: space-between;
        margin-bottom: 10px;
      }

      .todo-input input {
        flex: 1;
        padding: 8px;
        border: 1px solid #ccc;
        border-radius: 5px;
      }

      .todo-input button {
        padding: 8px 12px;
        background: #28a745;
        color: white;
        border: none;
        cursor: pointer;
        margin-left: 5px;
        border-radius: 5px;
      }

      .todo-input button:hover {
        background: #218838;
      }

      ul {
        list-style: none;
        padding: 0;
      }

      li {
        padding: 10px;
        background: #f9f9f9;
        margin: 5px 0;
        display: flex;
        justify-content: space-between;
        border-radius: 5px;
      }

      li button {
        background: #dc3545;
        border: none;
        color: white;
        padding: 5px;
        cursor: pointer;
        border-radius: 5px;
      }

      li button:hover {
        background: #c82333;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>To-Do List</h1>
      <div class="todo-input">
        <input type="text" id="taskInput" placeholder="Add a new task..." />
        <button onclick="addTask()">Add</button>
      </div>
      <ul id="taskList"></ul>
    </div>

    <script>
      function addTask() {
        let taskInput = document.getElementById("taskInput");
        let taskValue = taskInput.value.trim();

        if (taskValue === "") {
          alert("Please enter a task!");
          return;
        }

        let taskList = document.getElementById("taskList");

        let li = document.createElement("li");
        li.innerHTML = `
          ${taskValue}
          <button onclick="removeTask(this)">Delete</button>
        `;

        taskList.appendChild(li);
        taskInput.value = "";
      }

      function removeTask(button) {
        let taskList = document.getElementById("taskList");
        let taskItem = button.parentElement;
        taskList.removeChild(taskItem);
      }
    </script>
  </body>
</html>

```
## OUTPUT
![image](https://github.com/user-attachments/assets/756177cc-c623-4c2e-8cf3-af89110877ae)


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
