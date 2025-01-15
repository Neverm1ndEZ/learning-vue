<script setup>
	import Hero from "@/components/Hero.vue";
	import HomeCards from "@/components/HomeCards.vue";
	import JobListings from "@/components/JobListings.vue";
</script>

<template>
	<!-- Eg of props -->
	<!-- <Hero title="Test Title" subTitle="test sub" /> -->
	<Hero />
	<HomeCards />
	<JobListings :limit="3" :showButton="true" />
</template>
