<template>
  <div class="t-todo-app">
    <TodoApp />
  </div>
</template>

<script>
import Todo from './components/TodoApp.vue';
export default {
  components: {
    TodoApp: Todo
  }
}
</script>