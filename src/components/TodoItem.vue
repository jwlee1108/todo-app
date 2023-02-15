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
    return {}
  },
  methods: {
    changeComplete(todo) {
      this.$emit('todo-click', todo);
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
