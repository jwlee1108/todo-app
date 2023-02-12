<template>
  <ul>
    <li v-for="(todo, index) in todos" :key="index">
      {{ todo.title }}
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      todos: [
        { title: 'something to do' },
        { title: 'what I have to do' },
      ]
    }
  }
}
</script>
<style>
</style>
