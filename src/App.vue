<template>
  <div>
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos 
      v-bind:todos="todos" 
      v-on:del-todo="deleteTodo" 
      v-on:complete-todo="changeStatus"/>
  </div>
</template>

<script>
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';
import Header from './components/layout/Header';

export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo 1",
          completed: false
        },
        {
          id: 2,
          title: "Todo 2",
          completed: false
        },
        {
          id: 3,
          title: "Todo 3",
          completed: false
        },
        
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter( todo => todo.id !== id)
    },
    changeStatus(id) {
      this.todos.forEach(todo => todo.id === id ? todo.completed = !todo.completed : '')
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    }
  }
}
</script>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
