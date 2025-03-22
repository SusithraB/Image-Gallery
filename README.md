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
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Todo Application</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f3e5f5; /* Light pastel purple */
            text-align: center;
        }
        header, footer {
            background-color: #b39ddb; /* Soft pastel purple */
            color: white;
            padding: 15px;
            font-size: 20px;
            font-weight: bold;
        }
        .todo-container {
            max-width: 400px;
            background: white;
            margin: 30px auto;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border: 2px solid #b39ddb;
        }
        .todo-input {
            width: 100%;
            padding: 10px;
            border: 2px solid #b39ddb;
            border-radius: 4px;
            margin-bottom: 10px;
        }
        .todo-list {
            list-style: none;
            padding: 0;
        }
        .todo-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            margin-bottom: 5px;
            background-color: #f3e5f5;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        .todo-item.completed span {
            text-decoration: line-through;
            color: gray;
        }
        .todo-buttons button {
            padding: 5px 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .complete-btn {
            background-color: #9575cd; /* Softer purple */
            color: white;
        }
        .delete-btn {
            background-color: #f48fb1; /* Soft pink for contrast */
            color: white;
        }
    </style>
</head>
<body>
    <header>Todo Application</header>
    <div class="todo-container">
        <h2>To-Do List ✅</h2>
        <input type="text" id="todo-input" class="todo-input" placeholder="Add a new task">
        <ul id="todo-list" class="todo-list"></ul>
    </div>
    <footer>&copy; 2025 Deepika S (212222230028) | All rights reserved.</footer>
    <script>
        const todoInput = document.getElementById('todo-input');
        const todoList = document.getElementById('todo-list');

        function addTodo() {
            const task = todoInput.value.trim();
            if (task === '') return;

            const li = document.createElement('li');
            li.className = 'todo-item';

            const span = document.createElement('span');
            span.textContent = task;

            const buttonsDiv = document.createElement('div');
            buttonsDiv.className = 'todo-buttons';

            const completeBtn = document.createElement('button');
            completeBtn.textContent = 'Complete';
            completeBtn.className = 'complete-btn';
            completeBtn.onclick = () => {
                li.classList.toggle('completed');
            };

            const deleteBtn = document.createElement('button');
            deleteBtn.textContent = 'Delete';
            deleteBtn.className = 'delete-btn';
            deleteBtn.onclick = () => {
                todoList.removeChild(li);
            };

            buttonsDiv.appendChild(completeBtn);
            buttonsDiv.appendChild(deleteBtn);

            li.appendChild(span);
            li.appendChild(buttonsDiv);

            todoList.appendChild(li);
            todoInput.value = '';
        }

        todoInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                addTodo();
            }
        });
    </script>
</body>
</html>

```
## OUTPUT
![todo list](https://github.com/user-attachments/assets/fb876770-5837-4054-b91a-3e6b72033a8d)
## RESULT
The program for creating To-do list using JavaScript is executed successfully.
