<template>
  <div>
    <div>
      <input type="text" v-model="newTodo" @keyup.enter="addTodo" />
      <button @click="addTodo">Add</button>
    </div>
    <ul>
      <li
          v-for="(todo, index) in todos"
          :key="index"
          @click="changeComplete(todo)"
          :class="{completed: todo.complete}"
      >
        <input type="checkbox" v-model="todo.complete"/>{{ todo.title }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      newTodo: '',
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
    },
    addTodo() {
      this.todos.push({ title: this.newTodo, complete: false });
      this.newTodo = '';
    }
  }
}
</script>
<style>
li {
  user-select: none;
}

.completed {
  text-decoration: line-through;
  color: #ddd;
}
</style>
