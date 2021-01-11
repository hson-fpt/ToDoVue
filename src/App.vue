<template>
  <div id="app">
    <a-row class="main-logo">
      <img alt="Vue logo" src="./assets/logo.png" />
    </a-row>

    <a-row class="main-container">
      <a-col :span="8" class="main-container-to-do-form">
        <ToDoForm @submitted="onSubmit" />
      </a-col>

      <a-col :span="16" class="main-container-to-do-table">
        <ToDoTable :tableData="tableData" />
      </a-col>
    </a-row>
  </div>
</template>

<script>
import Vue from "vue";
import Antd from "ant-design-vue";
import { Row, Col } from "ant-design-vue";

import ToDoTable from "./components/to-do-table/ToDoTable";
import ToDoForm from "./components/to-do-form/ToDoForm";

import "ant-design-vue/dist/antd.css";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

Vue.use(Antd, Row, Col);
export default {
  name: "App",
  components: {
    ToDoTable,
    ToDoForm
  },
  data() {
    return { tableData: [] };
  },
  methods: {
    onSubmit(data) {
      this.tableData.push(data);
    }
  }
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

.main-container {
  margin-top: 5vh;
}

.main-container-to-do-form {
  padding-right: 1vw;
}
</style>
