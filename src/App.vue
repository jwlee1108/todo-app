<template>
  <div>
    <button @click="shuffleFullName">Shuffle</button>
    <p>{{ fullName }}</p>
  </div>
</template>
<script>
const NAMES = [
  'John Doe',
  'Jane Doe',
  'John Smith',
  'Jane Smith'
];
export default {
  data() {
    return {
      firstName: 'John',
      lastName: 'Doe'
    }
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(newName) {
        const names = newName.split(' ');
        this.firstName = names[0];
        this.lastName = names[names.length - 1];
      }
    }
  },
  methods: {
    shuffleFullName() {
      this.fullName = NAMES[Math.floor(Math.random() * NAMES.length)];
    }
  }
}
</script>
<style>
</style>
