// options API (older vue shit)

<script>
	export default {
		data() {
			return {
				name: "John Doe",
				status: "pending",
				tasks: ["task 1", "task 2", "task 3"],
				link: "https://google.com",
			};
		},
		methods: {
			toggleStatus() {
				if (this.status === "active") {
					this.status = "pending";
				} else if (this.status === "pending") {
					this.status = "inactive";
				} else {
					this.status = "active";
				}
			},
		},
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

	<a :href="link">Google</a>

	<!-- <button v-on:click="toggleStatus">Change Status</button> -->
	<button @click="toggleStatus">Change Status</button>
</template>

<style scoped>
	h1 {
		color: red;
	}
</style>
