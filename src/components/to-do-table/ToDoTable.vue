<template>
	<fragment>
		<b-table
			class="sample-table"
			striped
			hover
			:items="dataTable"
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
		dataTable: Array,
	},

	data() {
		return {
			// items: this.dataTable,
		};
	},
};
</script>

<style>
.sample-table {
	border: 1px solid rgba(170, 167, 167, 0.911);
}
</style>
