<template>
  <ul>
    <li>{{ todo.title }}</li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      todo: {
        title: 'Learning Vue!'
      }
    }
  }
}
</script>
<style>
</style>
