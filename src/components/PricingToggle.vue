<template>
	<button v-on:click="toggle" :class="isActive ? `enabled` : `disabled`" class="pricing-toggle-button">
		<span class="pricing-button-ripple"></span>
	</button>
</template>

<script>
export default {
	name: "PricingToggle",
	props: {
		classNames: {
			type: String,
			default: "",
		},
	},
	data() {
		return {
			isActive: false,
		};
	},
	methods: {
		toggle() {
			this.isActive = !this.isActive;
		},
	},
};
</script>

<style scoped>
.pricing-toggle-button {
	align-items: center;
	border-radius: 40px;
	display: flex;
	height: 24px;
	padding: 6px;
	position: relative;
	width: 50px;
}

.pricing-button-ripple {
	background-color: var(--white);
	border-radius: 50%;
	display: inline-block;
	height: 18px;
	width: 18px;
	transition: transform 0.2s linear;
}

.pricing-toggle-button.disabled {
	background-color: var(--light-grayish-blue-1);
}

.pricing-toggle-button.enabled {
	background-color: var(--soft-cyan);
}

.pricing-toggle-button.enabled .pricing-button-ripple {
	transform: translate(20px, 0);
}

.pricing-toggle-button.disabled .pricing-button-ripple {
	transform: translate(0, 0);
}
</style>
