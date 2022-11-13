<template>
  <div>
    <div>Todo APP</div>
    <AddTodo v-on:add-todo="addTodo"></AddTodo>
    <hr />
    <TodoList v-bind:todos="todos" v-on:remove-todo="removeTodo"></TodoList>
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import AddTodo from "./components/AddTodo.vue";

export default {
  data() {
    return {
      todos: [
        { id: 1, title: "Tasck 1", complited: false },
        { id: 2, title: "Tasck 2", complited: false },
        { id: 3, title: "Tasck 3", complited: false },
      ],
    };
  },
  name: "App",
  components: {
    TodoList,
    AddTodo,
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((item) => item.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo)
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
