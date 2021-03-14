<template>
  <div class="container">
    <h2>Todo-Application</h2>
    <Form :add="add" />
    <ul class="list">
      <Todo
          v-for="(text, index) in todos"
          :todo="{text, index}"
          :key="text"
          :remove="remove"
      ></Todo>
    </ul>
  </div>
</template>

<script>
import Form from '@/components/Form';
import Todo from '@/components/Todo';
export default {
  name: 'App',
  components: { Form, Todo },
  methods: {
    add(name) {
      if (name)
        this.todos.push(name)
    },
    remove(index) {
      this.todos.splice(index, 1)
    }
  },
  data: () => {
    return {
      todos: []
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  max-width: 300px;
  margin: 0 auto;
}
.list {
  margin: 0;
  padding: 0;
}
</style>
