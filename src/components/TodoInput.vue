<template>
  <form class="todo-form" @submit.prevent="addTodo">
    <input type="text" name="text" id="text" placeholder="new task" />
    <button type="submit" id="todo-add-btn">Add Task</button>
  </form>
</template>

<script>
export default {
  methods: {
    addTodo() {
      this.$emit("add-todo", text.value);
      text.value = "";
    },
  },
};
</script>

<style scoped>
.todo-form {
  width: 320px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 20px auto;
}
#text {
  width: 200px;
  padding: 0px 5px;
  height: 42px;
  border-radius: 5px;
  border: 1px solid grey;
  font-size: 16px;
}
#todo-add-btn {
  height: 42px;
  background: ivory;
  border-radius: 5px;
  font-size: 12px;
  padding: 5px 20px;
  border: 1px solid grey;
  transition: all 0.5s;
}
#todo-add-btn:hover {
  background: rgb(223, 223, 219);
  cursor: pointer;
}
</style>
