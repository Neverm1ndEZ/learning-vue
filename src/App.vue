<!-- Composition API -->

<script setup>
	import { ref } from "vue";
	const name = ref("John Doe");
	const status = ref("active");
	const tasks = ref(["task 1", "task 2", "task 3"]);
	const newTask = ref("");

	const toggleStatus = () => {
		if (status.value === "active") {
			status.value = "pending";
		} else if (status.value === "pending") {
			status.value = "inactive";
		} else {
			status.value = "active";
		}
	};

	const addTask = () => {
		if (newTask.value.trim() !== "") {
			tasks.value.push(newTask.value);
			newTask.value = "";
		}
	};

	const deleteTask = (index) => {
		tasks.value.splice(index, 1);
	};
</script>
xs
<template>
	<h1>Vue Crash Course</h1>
	<h2>{{ name }}</h2>
	<p v-if="status === 'active'">User is active</p>
	<p v-else-if="status === 'pending'">User is pending</p>
	<p v-else>User is not active</p>

	<form @submit.prevent="addTask">
		<label for="newTask">Add Task</label>
		<input
			type="text"
			id="newTask"
			name="newTask"
			placeholder="add task"
			v-model="newTask"
		/>
		<button type="submit">Add Task</button>
	</form>

	<h3>Tasks</h3>
	<ul>
		<li v-for="(task, index) in tasks" :key="task">
			<span>{{ task }}</span>
			<button @click="deleteTask(index)">X</button>
		</li>
	</ul>

	<!-- <button v-on:click="toggleStatus">Change Status</button> -->
	<button @click="toggleStatus">Change Status</button>
</template>

<style scoped>
	h1 {
		color: red;
	}
</style>
