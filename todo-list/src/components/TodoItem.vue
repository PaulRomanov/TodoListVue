<template>
  <li>
    <span v-bind:class="{done: todo.complited}">
      <input type="checkbox" v-on:change="todo.complited = !todo.complited"/>
      {{ todo.id }}
      {{ todo.title }}
    </span>
    <button class="btn_del" v-on:click="$emit('remove-todo', todo.id)">&times;</button>
  </li>
</template>
<script>
export default {
  props: ["todo"],
};
</script>

<style scoped>
li {
  border: 1px solid black;
  display: flex;
  justify-content: space-between;
  margin: 10px;
  padding: 10px;
}
.btn_del {
  border-radius: 50%;
  background-color: brown;
  color: aliceblue;
}
.done {
  text-decoration: line-through;
}
</style>
