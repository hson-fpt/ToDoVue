<template>
	<a-row v-bind:class="[className, 'attribute-row']">
		<a-col :span="8" class="form-activity-label">{{ label }}</a-col>
		<a-col :span="16" class="form-activity-input">
			<a-input
				:placeholder="inputPlaceholder"
				:value="value"
				@input="dataInput"
			/>
		</a-col>
	</a-row>
</template>

<script>
import Vue from "vue";
import Antd, { Row, Col, Input } from "ant-design-vue";

Vue.use(Antd, Row, Col, Input);
export default {
	name: "ToDoFormLine",
	props: {
		className: String,
		label: String,
		inputPlaceholder: {
			type: String,
			default: "Please stay hydrate",
		},
		value: {
			type: String,
			default: "",
		},
	},

	methods: {
		dataInput(event) {
			this.$emit("input", event.target.value);
		},
	},
};
</script>

<style>
.attribute-row {
	margin-bottom: 1vh;
}
</style>
