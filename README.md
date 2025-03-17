# Ex03 To-Do List using JavaScript
## Date:16.03.20205

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
    <title>To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            text-align: center;
        }
        .container {
            width: 300px;
            margin: 50px auto;
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        .input-section {
            display: flex;
            gap: 10px;
        }
        input {
            flex: 1;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            padding: 8px 15px;
            border: none;
            background: #28a745;
            color: white;
            cursor: pointer;
            border-radius: 4px;
        }
        button:hover {
            background: #218838;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            background: #eee;
            padding: 10px;
            margin-top: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-radius: 4px;
            cursor: pointer;
        }
        .completed {
            text-decoration: line-through;
            color: gray;
        }
        .delete-btn {
            background: red;
            color: white;
            border: none;
            padding: 5px;
            cursor: pointer;
            border-radius: 4px;
        }
        .delete-btn:hover {
            background: darkred;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <div class="input-section">
            <input type="text" id="taskInput" placeholder="Add a new task...">
            <button id="addTaskBtn">Add Task</button>
        </div>
        <ul id="taskList"></ul>
    </div>
    <footer>
        <p>&copy; 2025 Susithra.B. All Rights Reserved.</p>
    </footer>
    <script>
        document.addEventListener("DOMContentLoaded", () => {
            const taskInput = document.getElementById("taskInput");
            const addTaskBtn = document.getElementById("addTaskBtn");
            const taskList = document.getElementById("taskList");

            loadTasks();

            addTaskBtn.addEventListener("click", addTask);
            
            function addTask() {
                const taskText = taskInput.value.trim();
                if (taskText === "") return;

                const li = document.createElement("li");
                li.innerHTML = `
                    <span class="task-text">${taskText}</span>
                    <button class="delete-btn">X</button>
                `;

                taskList.appendChild(li);
                saveTasks();

                taskInput.value = "";
                li.addEventListener("click", toggleComplete);
                li.querySelector(".delete-btn").addEventListener("click", deleteTask);
            }

            function toggleComplete(event) {
                event.target.classList.toggle("completed");
                saveTasks();
            }

            function deleteTask(event) {
                event.target.parentElement.remove();
                saveTasks();
            }

            function saveTasks() {
                const tasks = [];
                document.querySelectorAll("#taskList li").forEach((li) => {
                    tasks.push({
                        text: li.querySelector(".task-text").innerText,
                        completed: li.classList.contains("completed"),
                    });
                });
                localStorage.setItem("tasks", JSON.stringify(tasks));
            }

            function loadTasks() {
                const savedTasks = JSON.parse(localStorage.getItem("tasks")) || [];
                savedTasks.forEach((task) => {
                    const li = document.createElement("li");
                    li.innerHTML = `
                        <span class="task-text">${task.text}</span>
                        <button class="delete-btn">X</button>
                    `;
                    if (task.completed) li.classList.add("completed");

                    taskList.appendChild(li);
                    li.addEventListener("click", toggleComplete);
                    li.querySelector(".delete-btn").addEventListener("click", deleteTask);
                });
            }
        });
    </script>
</body>
</html>
```

## OUTPUT:
![image](https://github.com/user-attachments/assets/415dc073-d5dd-4b15-9fee-df8683181296)

![image](https://github.com/user-attachments/assets/e2fbfe27-0a23-4315-881e-936853c0a0d0)



## RESULT
The program for creating To-do list using JavaScript is executed successfully.
