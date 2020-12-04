<template>
  <div>
    <ul>
      <TodoItem
        v-for="(todo, i) in todos"
        :key="todo.id"
        v-bind:todo="todo"
        v-bind:index="i"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem';
export default {
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id);
    },
  },
  props: ['todos'],
  components: {
    TodoItem,
  },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
