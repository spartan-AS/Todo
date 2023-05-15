from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
    return render_template("index.html")

if __name__ == "__main__":
    app.run()
    <!DOCTYPE html>
<html>
<head>
    <title>Todo List</title>
    <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <div class="container">
        <h1>Todo List</h1>
        <form id="todo-form">
            <input type="text" id="task-input" placeholder="Enter a task">
            <button type="submit">Add</button>
        </form>
        <ul id="task-list"></ul>
    </div>

    <script src="{{ url_for('static', filename='script.js') }}"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    margin: 0;
    padding: 0;
}

.container {
    max-width: 600px;
    margin: 40px auto;
    background-color: #fff;
    padding: 20px;
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.1);
}

h1 {
    text-align: center;
    color: #333;
}
#task-input {
    width: 80%;
    padding: 10px;
    font-size: 16px;
}

button {
    padding: 10px 20px;
    background-color: #4caf50;
    color: #fff;
    border: none;
    cursor: pointer;
}

#task-list {
    margin-top: 20px;
    list-style-type: none;
}

.task {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 10px;
    margin-bottom: 10px;
    border-bottom: 1px solid #eee;
    }

.task .delete {
    color: #f44336;
    cursor: pointer;
}
document.getElementById("todo-form").addEventListener("submit", function(e) {
    e.preventDefault();
    
    var taskInput = document.getElementById("task-input");
    var taskList = document.getElementById("task-list");
    
    if (taskInput.value.trim() !== "") {
        var taskItem = document.createElement("li");
        taskItem.className = "task";
        taskItem.innerHTML = `
            <span>${taskInput.value}</span>
            <span class="delete">X</span>
        `;
        taskList.appendChild(taskItem);
        
        taskInput.value = "";
    }
});

document.getElementById("task-list").addEventListener("click", function(e) {
    if (e.target.className === "delete") {
        var taskItem = e.target.parentElement;
        taskItem.remove();
    }
});
