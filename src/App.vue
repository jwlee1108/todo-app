<template>
  <div>
    <input v-model="message" type="text" />
    <p>Text: {{ message }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      message: 'Hello Vue!'
    }
  }
}
</script>
<style>
</style>
