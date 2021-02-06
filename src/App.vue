<template>
	<div id="app">
		<Header />
	</div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
	name: "App",
	components: {
		Header,
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
