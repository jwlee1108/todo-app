<template>
  <li
    @click="changeComplete(todo)"
    :class="{completed: todo.complete}"
  >
    <input type="checkbox" v-model="todo.complete"/>
    {{ todo.title }}
  </li>
</template>
<script>
export default {
  name: 'TodoItem',
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      newTodo: '',
      todos: [],
      filter: 'total'
    }
  },
  watch: {
    todos(newTodos) {
      localStorage.setItem('todos', JSON.stringify(newTodos));
      console.log('todos updated');
    },
  },
  methods: {
    changeComplete(todo) {
      todo.complete = !todo.complete;
      console.log(`todo: ${todo.title} is ${todo.complete ? 'complete' : 'incomplete'}`);
    },
  }
}
</script>
<style>
li {
  user-select: none;
}

.completed {
  text-decoration: line-through;
  color: #ddd;
}
</style>
