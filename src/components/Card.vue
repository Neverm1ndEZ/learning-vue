<script setup>
	import { defineProps } from "vue";
	defineProps({
		bg: {
			type: String,
			default: "bg-gray-100",
		},
	});
</script>

<template>
	<div :class="`${bg} p-6 rounded-lg shadow-md`">
		<!-- // This is where the content will be injected kinda like {children} in React -->
		<slot></slot>
	</div>
</template>
