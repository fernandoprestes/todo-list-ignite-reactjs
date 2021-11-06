<div style="text-align: center;">
  <img src="https://www.notion.so/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F2fbacb7a-e460-44a3-8fc5-e66f96dae148%2Fcover-reactjs.png?table=block&id=57692167-7879-4019-a83f-544e79167b12&spaceId=08f749ff-d06d-49a8-a488-9846e081b224&width=2000&userId=6b184496-d59f-431e-9205-efb47de631f8&cache=v2" alt="trilha ignite reactjs" style="width:384px;"/>
</div>

---
<h1>Desafio 01 - Conceitos do React </h1>

<p>Essa será uma aplicação onde o seu principal objetivo é uma pequena aplicação de atividades a fazer, para treinar um pouco mais sobre manipulação do estado no React.<p>

- [x]  Adicionar uma nova tarefa
- [x]  Remover uma tarefa
- [x]  Marcar e desmarcar uma tarefa como concluída

<h2>Template da plicação</h2>
<p>O template está disponível na seguinte URL: <a href="https://github.com/rocketseat-education/ignite-template-reactjs-conceitos-do-react"> github.com/rocketseat-education/ignite-template-reactjs-conceitos-do-react</a></p>

<h2>Solução</h2>

`components/TaskList.tsx` é componente responsável por todas as funcionalidades da aplicação

<h3>Adicionar uma nova tarefa: handleCreateNewTask()</h3>

```
function handleCreateNewTask() {
    if(!newTaskTitle) return
    const newTask = {
      id: Math.random(),
      title: newTaskTitle,
      isComplete: false
    }

    setTasks(tasks => [...tasks, newTask])
    setNewTaskTitle('')
  }

```

<h3>Remover uma tarefa: handleRemoveTask(id: number)</h3>

```
function handleRemoveTask(id: number) {
    const filteredTasks = tasks.filter(task => task.id !== id)
    setTasks(filteredTasks)
  }
```

<h3>Marcar e desmarcar uma tarefa como concluída: handleToggleTaskCompletion(id: number)</h3>

```
function handleToggleTaskCompletion(id: number) {
    const task = tasks.map(task => task.id === id ? {
      ...task, 
      isComplete: !task.isComplete
    } : task)
    setTasks(task)
  }
```
---
Feito com 💜 por Rocketseat