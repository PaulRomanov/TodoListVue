<template>
  <!-- .prevent чтобы не перезагружалась форма -->
  <!-- v-model="title"  для получения доступа к value input -->
  <form v-on:submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Add todo</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      const newTodo = {
        id: Date.now(),
        title: this.title,
        complited: false,
      };
      this.$emit("add-todo", newTodo); //сообщаем app component о событии
      this.title = "";  //для очистки input
    },
  },
};
</script>
