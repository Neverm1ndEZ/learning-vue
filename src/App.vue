<!-- Composition API -->

<script setup>
	import { ref } from "vue";
	const name = ref("John Doe");
	const status = ref("active");
	const tasks = ref(["task 1", "task 2", "task 3"]);

	const toggleStatus = () => {
		if (status.value === "active") {
			status.value = "pending";
		} else if (status.value === "pending") {
			status.value = "inactive";
		} else {
			status.value = "active";
		}
	};
</script>

<template>
	<h1>Vue Crash Course</h1>
	<h2>{{ name }}</h2>
	<p v-if="status === 'active'">User is active</p>
	<p v-else-if="status === 'pending'">User is pending</p>
	<p v-else>User is not active</p>

	<h3>Tasks</h3>
	<ul>
		<li v-for="task in tasks" :key="task">{{ task }}</li>
	</ul>

	<!-- <button v-on:click="toggleStatus">Change Status</button> -->
	<button @click="toggleStatus">Change Status</button>
</template>

<style scoped>
	h1 {
		color: red;
	}
</style>
