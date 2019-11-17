<template>
  <div id="app">
    <Title
      msg="Список дел"
    />
    <AddTodo
      @add-task="addTask"
    />
    <List
      :todos="todos"
      @delete-item="deleteItem"
      @add-task="addTask"
    />
  </div>
</template>

<script>
import List from './components/List.vue'
import AddTodo from './components/AddTodo.vue'
import Title from './components/Title.vue'

export default {
  name: 'app',
  data() {
    return {
      todos: [
        {
          text: 'Купить хлеб',
          done: false,
          id: 1,
        }, {
          text: 'Купить молоко',
          done: false,
          id: 2,
        }, {
          text: 'Купить макароны',
          done: false,
          id: 3,
        },
      ]
    }
  },
  methods: {
    deleteItem(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTask(task) {
      this.todos.push(task)
    }
  },
  components: {
    List, Title, AddTodo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
