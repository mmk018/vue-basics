<template>
  <div id="app">
    <h1>To do APP</h1>
    <TodoInput v-on:add-todo="addTodo"></TodoInput>
    <TodoList v-bind:todos="todos" @remove-todo="removeTodo"></TodoList>
  </div>
</template>

<script>
import { uuid } from "vue-uuid";
import TodoList from "@/components/TodoList";
import TodoInput from "@/components/TodoInput";
export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: this.uuidN(), title: "buy bread", completed: false },
        { id: this.uuidN(), title: "buy milk", completed: false },
        { id: this.uuidN(), title: "buy juice", completed: false },
      ],
    };
  },
  components: {
    TodoInput,
    TodoList,
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id);
    },
    addTodo(title) {
      const newTodo = {
        title,
        id: this.uuidN(),
        completed: false,
      };
      this.todos.push(newTodo);
    },
    uuidN() {
      const n = uuid.v4();
      return n;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
