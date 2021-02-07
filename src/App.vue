<template>
	<div id="app">
		<app-header />
		<pricing-card :plans="plans" />
	</div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import PricingCard from "./components/PricingCard.vue";
import { plans } from "./fixtures/plans";

export default {
	name: "App",
	components: {
		AppHeader,
		PricingCard,
	},
	data() {
		return {
			plans: plans,
		};
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
