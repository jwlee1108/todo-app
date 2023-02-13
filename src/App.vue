<template>
  <div>
    <input type="checkbox" v-model="checkFlag" />
    <p>checkFlag: {{ checkFlag }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      checkFlag: false
    }
  }
}
</script>
<style>
</style>
