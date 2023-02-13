<template>
  <ul>
    <li v-for="(todo, index) in todos" :key="index">
      <input type="checkbox" :checked="todo.complete"/>{{ todo.title }}
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      todos: [
        { title: 'something to do', complete: true },
        { title: 'what I have to do', complete: false },
      ]
    }
  }
}
</script>
<style>
</style>
