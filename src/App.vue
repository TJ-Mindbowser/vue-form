<template>
  <div id="app">
    <input
      @keyup.enter="handleTodo"
      v-model.trim.lazy="message"
      placeholder="Enter Todo"
    />
    <div>
      <ul>
        <li @click="removeItem" v-for="todo in todos">{{ todo }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: '',
      todos: [],
    };
  },
  methods: {
    handleTodo() {
      this.message && this.todos.push(this.message);
      console.log(this.todos);
    },
    removeItem() {},
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
ul {
  list-style: none;
}
</style>
