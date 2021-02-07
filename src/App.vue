<template>
	<div id="app">
		<app-header />
		<pricing-card />
	</div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import PricingCard from "./components/PricingCard.vue";

export default {
	name: "App",
	components: {
		AppHeader,
		PricingCard,
	},
};
</script>

<style>
#app {
	align-items: flex-start;
	display: flex;
	flex-direction: column;
	min-height: 100vh;
	min-width: 360px;
	width: 100%;
}
</style>
