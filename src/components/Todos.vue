<template>
  <div class="todos">
    <div v-bind:key="todo.id" v-for="todo in todos">
      <Todo
        v-bind:todo="todo"
        v-on:delete-todo="$emit('delete-todo', todo.id)"
      />
    </div>
  </div>
</template>

<script>
import Todo from "./Todo";

export default {
  name: "Todos",
  components: {
    Todo,
  },
  props: ["todos"],
};
</script>

<style scoped>
.todos {
  max-width: 800px;
  width: 100%;
  margin: 0 auto;
}
</style>
