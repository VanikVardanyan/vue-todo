<template>
  <div id="app">
    <h1>Todo</h1>
    <AddTodo @addTodo="addTodo" />
    <hr />
    <TodoList v-bind:todos="todos" v-on:remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList';
import AddTodo from '@/components/addTodoComponent';
export default {
  name: 'App',
  components: {
    TodoList,
    AddTodo,
  },
  data() {
    return {
      todos: [
        { id: 1, title: 'this isisis', completed: false },
        { id: 2, title: 'hahaha', completed: false },
        { id: 3, title: 'jnjsnj', completed: false },
      ],
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
