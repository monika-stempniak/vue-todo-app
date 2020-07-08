<template>
  <div class="todo">
    <div class="title-container">
      <input type="checkbox" v-on:change="markAsComplete" />
      <p class="title" v-bind:class="{ completed: todo.completed }">
        {{ todo.title }}
      </p>
    </div>
    <button class="delete" @click="$emit('delete-todo', todo.id)">x</button>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    markAsComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todo {
  background: cornsilk;
  padding: 10px;
  border-bottom: 3px solid white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 5px;
}

.title-container {
  display: flex;
  align-items: center;
}

.title {
  margin-left: 10px;
  margin-right: 10px;
}

.completed {
  text-decoration: line-through;
}

.delete {
  background: brown;
  color: white;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
