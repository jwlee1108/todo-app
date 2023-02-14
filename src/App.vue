<template>
  <div>
    <button @click="addLeftOperand">Add num1</button>
    <button @click="addRightOperand">Add num2</button>
    <p>{{ sum }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      leftOperand: 0,
      rightOperand: 0
    }
  },
  computed: {
    sum() {
      return this.leftOperand + this.rightOperand;
    }
  },
  methods: {
    addLeftOperand() {
      this.leftOperand += 1;
      console.log(`leftOperand: ${this.leftOperand}`);
    },
    addRightOperand() {
      this.rightOperand += 1;
      console.log(`rightOperand: ${this.rightOperand}`);
    }
  }
}
</script>
<style>
</style>
