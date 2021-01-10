<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <ToDoTable />
  </div>
</template>

<script>
import ToDoTable from "./components/to-do-table/ToDoTable";

export default {
  name: "App",
  components: {
    ToDoTable,
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
