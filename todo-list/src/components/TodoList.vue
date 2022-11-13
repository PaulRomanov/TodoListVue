<template>
  <div>
    <ul>
     <TodoItem 
     v-for="t of todos"
     :key="t"
     v-bind:todo="t"
     v-on:remove-todo="removeTodo"
     ></TodoItem>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  props: ['todos'],
  components: {
    TodoItem
  },
  methods:{
    removeTodo(id){
      this.$emit('remove-todo', id)
    }
  }
}
</script>

<style scoped>
ul{
  list-style: none;
}
</style>