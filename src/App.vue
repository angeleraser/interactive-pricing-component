<template>
	<div id="app">
		<app-header />
		<slider-bar />
	</div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import SliderBar from "./components/SliderBar";

export default {
	name: "App",
	components: {
		SliderBar,
		AppHeader,
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
