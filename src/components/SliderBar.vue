<template>
	<div :class="classNames" class="slider-bar-wrapper">
		<span aria-label="input range bar" class="bar slider-background"></span>

		<span :style="getFillWidth" class="slider-fill bar"></span>

		<button v-bind:style="getControlPosition" class="slider-control">
			<svg xmlns="http://www.w3.org/2000/svg" style="transform: translateY(2px)" width="22" height="13">
				<g fill="#80FFF3" fill-rule="evenodd">
					<path
						d="M16 2.558v7.884a1 1 0 001.735.679l3.639-3.943a1 1 0 000-1.356l-3.64-3.943A1 1 0 0016 2.558zM6 2.558v7.884a1 1 0 01-1.735.679L.626 7.178a1 1 0 010-1.356l3.64-3.943A1 1 0 016 2.558z"
					/>
				</g>
			</svg>
		</button>

		<input v-model="inputValue" v-on:change="calculatePricing" type="range" :max="maxValue" :min="minValue" />
	</div>
</template>

<script>
export default {
	name: "SliderBar",
	props: {
		value: {
			type: Number,
			default: 0,
		},
		maxValue: {
			type: Number,
			default: 100,
		},
		minValue: {
			type: Number,
			default: 0,
		},
		classNames: {
			type: String,
			default: "",
		},
	},
	data() {
		return {
			inputValue: this.$props.value,
		};
	},
	methods: {
		calculatePricing() {
			console.log(this.inputValue);
		},
	},
	computed: {
		getControlPosition() {
			const currentPosition = this.inputValue;
			return `left:${currentPosition}%`;
		},
		getFillWidth() {
			const currentPosition = this.inputValue;
			return `width:${currentPosition}%`;
		},
	},
};
</script>

<style scoped>
input[type="range"],
input[type="range"]::-webkit-slider-runnable-track,
input[type="range"]::-webkit-slider-thumb {
	-webkit-appearance: none;
	cursor: pointer;
}

input[type="range"]::-webkit-slider-thumb {
	width: 40px;
	height: 40px;
	border-radius: 50%;
}

input[type="range"]::-moz-range-thumb {
	width: 40px;
	height: 40px;
	border-radius: 50%;
}

input[type="range"]::-ms-thumb {
	width: 40px;
	height: 40px;
	border-radius: 50%;
}

input[type="range"] {
	opacity: 0;
}

.slider-bar-wrapper {
	position: relative;
	width: 100%;
	height: 8px;
	max-width: 95%;
	align-self: center;
}

.slider-bar-wrapper input[type="range"] {
	width: 100%;
	position: absolute;
	top: 50%;
	transform: translateY(-50%);
	height: 10px;
	z-index: 80;
}

.slider-bar-wrapper .bar {
	display: inline-flex;
	height: 100%;
	width: 100%;
	position: absolute;
	border-radius: 12px;
}

.slider-bar-wrapper .slider-background {
	z-index: 10;
	background-color: var(--light-grayish-blue-1);
}

.slider-bar-wrapper .slider-fill {
	z-index: 20;
	background-color: var(--strong-cyan);
	width: 50%;
}

.slider-bar-wrapper .slider-control {
	width: 40px;
	height: 40px;
	border-radius: 50%;
	background-color: var(--strong-cyan);
	z-index: 30;
	top: 50%;
	left: 0;
	position: absolute;
	transform: translate(-20px, -20px);
	box-shadow: 0 10px 40px var(--strong-cyan);
}
</style>
