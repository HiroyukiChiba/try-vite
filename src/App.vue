<template>
  <Todo :todos="state.todos" @add-todo="addTodo" />
</template>

<script>
import {reactive} from 'vue';
import Todo from './components/Todo.vue'

export default {
  components: {
    Todo
  },
  setup () {
    const state = reactive({
      todos: ['ネギ']
    });
    const addTodo = (todo) => {
      state.todos.push(todo)
    }
    return {
      state,
      addTodo
    }
  }
}
</script>
