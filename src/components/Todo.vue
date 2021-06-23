<template>
  <div>
    <input v-model="state.newTodo" type="text">
    <button type="button" @click="addTodo">追加</button>
  </div>
  <ul>
    <li v-for="todo in todos">
      <input type="checkbox">
      <span>{{ todo }}</span>
    </li>
  </ul>
</template>

<script>
import {reactive} from 'vue'

export default {
  props: {
    todos: {required: true, type: Array}
  },
  setup(props, context) {
    const state = reactive({
      newTodo: null
    });
    const addTodo = () => {
      console.log(state.newTodo)
      context.emit('add-todo', state.newTodo);
    };
    return {
      state,
      addTodo,
    }
  }
}
</script>
