<template>
  <div>
    <ul>
     <TodoItem></TodoItem>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  components: {
    TodoItem
  }
}
</script>