<template>
  <div>
    <button @click="count += 1">Add 1</button>
    <p>You clicked {{ count }} times.</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>
<style>
</style>
