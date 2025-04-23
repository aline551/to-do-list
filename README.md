# to-do-list
Lista de tarefas simples com HTML, CSS e JavaScript
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>To-Do List - Aline</title>
  <style>
    body {
      font-family: "Segoe UI", sans-serif;
      background: #f8f4f6;
      color: #2e1a1b;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 4rem 1rem;
    }

    .todo-container {
      background: #fff;
      padding: 2rem;
      border-radius: 16px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
      max-width: 400px;
      width: 100%;
    }

    h1 {
      color: #6a0f27;
      text-align: center;
      margin-bottom: 1.5rem;
    }

    input[type="text"] {
      width: 100%;
      padding: 0.8rem;
      border: 1px solid #ccc;
      border-radius: 8px;
      margin-bottom: 1rem;
      font-size: 1rem;
    }

    button {
      width: 100%;
      padding: 0.8rem;
      background-color: #9a1750;
      color: #fff;
      border: none;
      border-radius: 8px;
      font-size: 1rem;
      cursor: pointer;
    }

    button:hover {
      background-color: #6a0f27;
    }

    ul {
      list-style: none;
      padding: 0;
      margin-top: 1rem;
    }

    li {
      background: #ffd6e0;
      margin-bottom: 0.5rem;
      padding: 0.8rem;
      border-radius: 8px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    li.completed {
      text-decoration: line-through;
      color: #888;
      background: #f1f1f1;
    }

    .delete-btn {
      background: transparent;
      border: none;
      color: #9a1750;
      font-size: 1.2rem;
      cursor: pointer;
    }

    .delete-btn:hover {
      color: #6a0f27;
    }
  </style>
</head>
<body>

  <div class="todo-container">
    <h1>Minha Lista de Tarefas</h1>
    <input type="text" id="taskInput" placeholder="Digite uma tarefa..." />
    <button onclick="addTask()">Adicionar</button>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      const input = document.getElementById("taskInput");
      const taskText = input.value.trim();

      if (taskText === "") {
        alert("Digite uma tarefa!");
        return;
      }

      const li = document.createElement("li");

      li.textContent = taskText;

      li.addEventListener("click", () => {
        li.classList.toggle("completed");
      });

      const deleteBtn = document.createElement("button");
      deleteBtn.textContent = "✕";
      deleteBtn.className = "delete-btn";
      deleteBtn.onclick = () => li.remove();

      li.appendChild(deleteBtn);
      document.getElementById("taskList").appendChild(li);
      input.value = "";
    }
  </script>

</body>
</html>
