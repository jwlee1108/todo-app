<template>
  <ul>
    <li v-for="(todo, index) in todos" :key="index"  @click="changeComplete(todo)">
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
  },
  methods: {
    changeComplete(todo) {
      todo.complete = !todo.complete;
      console.log(`todo: ${todo.title} is ${todo.complete ? 'complete' : 'incomplete'}`);
    }
  }
}
</script>
<style>
li {
  user-select: none;
}
</style>
