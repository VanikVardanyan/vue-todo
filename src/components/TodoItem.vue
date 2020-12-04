<template>
  <li>
    <span v-bind:class="{ done: todo.completed }">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
      <strong>{{ index + 1 }}</strong>
      {{ todo.title }}
    </span>
    <button class="rm" v-on:click="$emit('remove-todo', todo.id)">
      &times;
    </button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
    },
    index: Number,
  },
};
</script>

<style scoped>
li {
  display: flex;
  justify-content: space-between;
  padding: 10px 15px;
  margin-bottom: 8px;
}

input {
  margin-right: 20px;
}

.rm {
  cursor: pointer;
  border: 1px solid green;
}

.done {
  text-decoration: line-through;
}
</style>
