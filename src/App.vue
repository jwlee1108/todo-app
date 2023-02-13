<template>
  <div>
    <button v-on:click="count('Increment')">Add 1</button>
    <button v-on:click="count('Decrement')">Sub 1</button>
    <p>counter: {{ counter }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    count(action) {
      if (action === 'Increment') {
        this.counter += 1;
      } else if (action === 'Decrement') {
        this.counter -= 1;
      }
    }
  }
}
</script>
<style>
</style>
