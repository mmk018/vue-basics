<template>
  <li>
    <span v-bind:class="{ done: todo.completed }">
      <input v-on:change="todo.completed = !todo.completed" type="checkbox" />
      <strong>{{ number }}</strong>
      {{ todo.title }}
    </span>
    <button class="rm" v-on:click="$emit('remove-todo', todo.id)">
      &times;
    </button>
  </li>
</template>
<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    number: {
      type: Number,
      required: true,
    },
  },
};
</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 2rem;
  margin-bottom: 1rem;
}
.rm {
  background: rgb(245, 111, 111);
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
  transition: all 0.5s;
}
.rm:hover {
  background: rgb(255, 0, 0);
  cursor: pointer;
}
.done {
  text-decoration: line-through;
}
input {
  margin-right: 1rem;
}
</style>
