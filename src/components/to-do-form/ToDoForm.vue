<template>
  <fragment>
    <ToDoFormLine
      className="form-activity-priority"
      label="Priority"
      v-model="dataInput.priorityInput"
    />
    <ToDoFormLine
      className="form-activity-start"
      label="Start"
      v-model="dataInput.startTimeInput"
    />
    <ToDoFormLine
      className="form-activity-task"
      label="Task"
      v-model="dataInput.taskInput"
    />
    <ToDoFormLine
      className="form-activity-end"
      label="End"
      v-model="dataInput.endTimeInput"
    />
    <ToDoFormLine
      className="form-activity-signature"
      label="Signature"
      v-model="dataInput.signatureInput"
    />
    <a-row class="form-button-row">
      <a-col :span="12">
        <a-button
          type="primary"
          class="form-submit-button"
          @click="btnSubmitClicked"
        >
          Add To List
        </a-button>
      </a-col>
      <a-col :span="12">
        <a-button
          type="primary"
          class="form-submit-button"
          @click="btnResetClicked"
        >
          Reset
        </a-button>
      </a-col>
    </a-row>
  </fragment>
</template>

<script>
import Vue from "vue";
import { Fragment } from "vue-fragment";
import Antd, { Row, Col, Button } from "ant-design-vue";

import ToDoFormLine from "./ToDoFormLine.vue";

Vue.use(Antd, Row, Col, Button, Fragment);
export default {
  name: "ToDoForm",
  components: {
    ToDoFormLine
  },

  data() {
    return {
      dataInput: {
        priorityInput: "",
        startTimeInput: "",
        taskInput: "",
        endTimeInput: "",
        signatureInput: ""
      }
    };
  },
  methods: {
    btnSubmitClicked() {
      this.$emit("submitted", this.dataInput);
    },

    btnResetClicked() {
      this.dataInput.priorityInput = "";
      this.dataInput.startTimeInput = "";
      this.dataInput.taskInput = "";
      this.dataInput.endTimeInput = "";
      this.dataInput.signatureInput = "";
    }
  }
};
</script>

<style></style>
