<template>
  <div class="todo">
    <h1>This is a ToDo App</h1>
    <form @submit.prevent="addNewTodo">
      <label>New Todo</label>
      <input v-model="newTodo" name="newTodo" />
      <button>Add New ToDo</button>
      <ul v-for="( todo, index) in todos" :key="todo.id">
        <!-- :class="{ done: todo.done }" -->
        <li>
          <p @click="toggleDone(todo)" :class="todo.done ? 'done' : 'not-done'">{{ todo.content }}</p>
          <button @click="removeTodo(index, todo)">Remove Todo</button>
          <button class="done-button" @click.prevent="toggleDone(todo)">Mark Done</button>
        </li>
      </ul>
    </form>
  </div>
</template>


<script>
import { ref } from 'vue'
export default {
  setup() {
    const newTodo = ref('')
    const todos = ref([])

    const removeTodo = (index, todo) => {
      todos.value.splice(index, 1)
    }
    const toggleDone = (todo) => {
      todo.done = !todo.done
    }
    const addNewTodo = () => {
      console.log(newTodo.value)
      todos.value.push({
        id: Date.now,
        done: false,
        content: newTodo.value
      })
      newTodo.value = ''
    }
    return {
      addNewTodo,
      newTodo,
      todos,
      toggleDone,
      removeTodo
    }
  }
}
</script>

<style scoped>
.todo {
  display: flex;
  flex-direction: column;
}

ul {}

li {
  cursor: pointer;
}

.done {
  text-decoration: line-through;
}
</style>