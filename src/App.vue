<template>
  <div>
    <button @click="addCount">Add 1</button>
    <p>You clicked {{ count }} times.</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    addCount() {
      this.count += 1;
    }
  }
}
</script>
<style>
</style>
