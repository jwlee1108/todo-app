<template>
  <div>
    <div class="counter-view">
      <button @click="setFilter('total')">Total: {{ totalCount }}</button>
      <button @click="setFilter('complete')">Complete: {{ completeCount }}</button>
      <button @click="setFilter('incomplete')">Incomplete: {{ incompleteCount }}</button>
    </div>
    <div class="control-view">
      <input type="text" v-model="newTodo" @keyup.enter="addTodo" />
      <button @click="addTodo">Add</button>
    </div>
    <ul>
      <li
          v-for="todo in filteredTodos"
          :key="todo.id"
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
      todos: [],
      filter: 'total'
    }
  },
  computed: {
    totalCount() {
      return this.todos.length;
    },
    completeCount() {
      return this.todos.filter(todo => todo.complete).length;
    },
    incompleteCount() {
      return this.todos.filter(todo => !todo.complete).length;
    },
    filteredTodos() {
      switch (this.filter) {
        case 'total':
          return this.todos;
        case 'complete':
          return this.todos.filter(todo => todo.complete);
        case 'incomplete':
          return this.todos.filter(todo => !todo.complete);
      }
    }
  },
  methods: {
    changeComplete(todo) {
      todo.complete = !todo.complete;
      console.log(`todo: ${todo.title} is ${todo.complete ? 'complete' : 'incomplete'}`);
    },
    addTodo() {
      this.todos.push({ title: this.newTodo, complete: false, id: +new Date() });
      this.newTodo = '';
    },
    setFilter(filter) {
      this.filter = filter;
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
