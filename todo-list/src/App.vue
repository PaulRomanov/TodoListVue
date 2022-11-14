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
      todos: [],
    };
  },
  name: "App",
  components: {
    TodoList,
    AddTodo,
  },
  //компонент подготовил HTML и поместил его в DOM
  //https://jsonplaceholder.typicode.com/
  //для генерации todo, что-бы указать по умолчанию кол-во: ?_limit=3
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=3")
      .then((response) => response.json())
      .then(json => {this.todos = json})
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((item) => item.id !== id);
    },
    addTodo(todo) {
      this.todos.push(todo);
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
