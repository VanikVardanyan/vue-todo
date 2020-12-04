<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">add todo</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: '',
    };
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        const newTodo = {
          title: this.title,
          id: Date.now(),
          completed: false,
        };

        this.$emit('addTodo', newTodo);
        this.title = '';
      }
    },
  },
};
</script>
