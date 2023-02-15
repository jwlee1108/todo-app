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
      <todo-item
        v-for="todo in filteredTodos"
        :key="todo.id"
        :todo="todo"
      />
    </ul>
  </div>
</template>
<script>
import TodoItem from '@/components/TodoItem.vue';
export default {
  components: {
    TodoItem
  },
  data() {
    return {
      newTodo: '',
      todos: [],
      filter: 'total'
    }
  },
  watch: {
    todos(newTodos) {
      localStorage.setItem('todos', JSON.stringify(newTodos));
      console.log('todos updated');
    },
    // todos: {
    //   handler(newTodos) {
    //     localStorage.setItem('todos', JSON.stringify(newTodos));
    //     console.log('todos updated');
    //   },
    //   deep: true
    // }
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
</style>
