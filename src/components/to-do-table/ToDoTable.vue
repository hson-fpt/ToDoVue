/* eslint-disable prettier/prettier */
<template>
  <fragment>
    <b-table
      class="sample-table"
      striped
      hover
      :items="tableData"
      :fields="fields"
    ></b-table>
  </fragment>
</template>

<script>
import Vue from "vue";
import { Fragment } from "vue-fragment";
import { BootstrapVue, IconsPlugin, TablePlugin } from "bootstrap-vue";

Vue.use(BootstrapVue, IconsPlugin, Fragment, TablePlugin);

export default {
  name: "ToDoTable",
  props: {
    textButton: String,
    tableData: Array
  },

  watch: {
    tableData: function(val) {
      console.log("val", val);
    }
  },

  data() {
    return {
      items: this.tableData,
      fields: [
        { key: "priorityInput", label: "Priority" },
        { key: "startTimeInput", label: "Start Time" },
        { key: "taskInput", label: "Task" },
        { key: "endTimeInput", label: "End Time" },
        { key: "signatureInput", label: "Signature" }
      ]
    };
  }
};
</script>

<style>
.sample-table {
  border: 1px solid rgba(170, 167, 167, 0.911);
}
</style>
