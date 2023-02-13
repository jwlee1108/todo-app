<template>
  <p>{{ sum }}</p>
</template>
<script>
export default {
  data() {
    return {
      num1: 3,
      num2: 4
    }
  },
  computed: {
    sum() {
      return this.num1 + this.num2
    }
  }
}
</script>
<style>
</style>
