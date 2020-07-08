<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        name="title"
        placeholder="Add Todo..."
        v-model="title"
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  margin: 0 auto;
  padding: 20px 10px;
  max-width: 800px;
  width: 100%;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
  border-radius: 5px;
  border: 1px solid #333;
}

input[type="submit"] {
  flex: 2;
  cursor: pointer;
  border: none;
  background-color: chocolate;
  color: white;
  text-transform: uppercase;
  border-radius: 5px;
  margin-left: 10px;
  padding: 0 5px;
}
</style>
