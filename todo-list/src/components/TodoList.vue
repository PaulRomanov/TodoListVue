<template>
  <div>
    <ul>
      <!-- i - доплнительная переменная, для отображения ID -->
      <TodoItem
        v-for="(t, i) of todos"
        :key="t"
        v-bind:todo="t"
        v-bind:indexId="i"
        v-on:remove-todo="removeTodo"
      ></TodoItem>
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>
<!-- Когда у тега <style> есть атрибут scoped, 
  то его CSS будет применяться только к элементам текущего компонента.  -->
<style scoped>
ul {
  list-style: none;
}
</style>
