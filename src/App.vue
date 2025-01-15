<script setup>
	import Hero from "./components/Hero.vue";
	import HomeCards from "./components/HomeCards.vue";
	import JobListings from "./components/JobListings.vue";
	import Navbar from "./components/Navbar.vue";
</script>

<template>
	<Navbar />
	<!-- Eg of props -->
	<!-- <Hero title="Test Title" subTitle="test sub" /> -->
	<Hero />
	<HomeCards />
	<JobListings :limit="3" :showButton="true" />
</template>
