<template>
	<fragment>
		<ToDoFormLine
			className="form-activity-priority"
			label="Priority"
			v-model="priorityInput.priorityInput"
		/>
		<ToDoFormLine
			className="form-activity-start"
			label="Start"
			v-model="priorityInput.priorityStartTime"
		/>
		<ToDoFormLine
			className="form-activity-task"
			label="Task"
			v-model="priorityInput.priorityTask"
		/>
		<ToDoFormLine
			className="form-activity-end"
			label="End"
			v-model="priorityInput.priorityEndTime"
		/>
		<ToDoFormLine
			className="form-activity-signature"
			label="Signature"
			v-model="priorityInput.prioritySignature"
		/>
		<a-row class="form-button-row">
			<a-col :span="12">
				<a-button
					type="primary"
					class="form-submit-button"
					@click="btnClicked"
				>
					Add To List
				</a-button>
			</a-col>
			<a-col :span="12">
				<a-button type="primary" class="form-submit-button">
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
		ToDoFormLine,
	},

	data() {
		return {
			priorityInput: {
				priorityInput: "",
				priorityStartTime: "",
				priorityTask: "",
				priorityEndTime: "",
				prioritySignature: "",
			},
		};
	},
	methods: {
		btnClicked() {
			this.$emit("submitted", this.priorityInput);
		},
	},
};
</script>

<style></style>
