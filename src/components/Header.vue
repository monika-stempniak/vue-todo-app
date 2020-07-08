<template>
  <header class="header">
    <h1>Todo-List</h1>
    <div>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.header {
  background: #333;
  color: white;
  text-align: center;
  padding: 10px;
  text-transform: uppercase;
}

.header a {
  color: white;
  padding-right: 10px;
  text-decoration: none;
  font-size: 14px;
}

.header a:last-child {
  margin-left: 8px;
}

.header a.router-link-exact-active {
  color: chocolate;
}
</style>
