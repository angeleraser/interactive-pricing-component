<template>
	<div :class="classNames" class="slider-bar-wrapper">
		<span aria-label="input range bar" class="bar slider-background"></span>

		<span :style="getFillWidth" class="slider-fill bar"></span>

		<input v-model="inputValue" type="range" :step="step" :max="maxValue" :min="minValue" />

		<button :style="getControlPosition" class="slider-control">
			<svg xmlns="http://www.w3.org/2000/svg" width="22" height="13">
				<g fill="#10FFF3" fill-rule="evenodd">
					<path
						d="M16 2.558v7.884a1 1 0 001.735.679l3.639-3.943a1 1 0 000-1.356l-3.64-3.943A1 1 0 0016 2.558zM6 2.558v7.884a1 1 0 01-1.735.679L.626 7.178a1 1 0 010-1.356l3.64-3.943A1 1 0 016 2.558z"
					/>
				</g>
			</svg>
		</button>
	</div>
</template>

<script>
export default {
	name: "SliderBar",
	props: {
		value: {
			default: 0,
		},
		maxValue: {
			type: Number,
			default: 200,
		},
		minValue: {
			type: Number,
			default: 0,
		},
		step: {
			type: Number,
			default: 1,
		},
		classNames: {
			type: String,
			default: "",
		},
		onPlanChange: {
			type: Function,
			required: true,
		},
	},
	data() {
		return {
			inputValue: this.$props.value,
		};
	},
	methods: {
		calcPercentageFor(ruleName) {
			const currentPosition = this.inputValue;

			const maxValue = this.$props.maxValue;

			const calculatedPosition = (currentPosition * 100) / maxValue;

			return `${ruleName}:${calculatedPosition}%`;
		},
		selectPlanIndex() {
			this.$props.onPlanChange(this.inputValue);
		},
	},
	computed: {
		getControlPosition() {
			this.selectPlanIndex();
			return this.calcPercentageFor("left");
		},
		getFillWidth() {
			return this.calcPercentageFor("width");
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
	width: 45px;
	height: 45px;
	border-radius: 50%;
}

input[type="range"]::-moz-range-thumb {
	width: 45px;
	height: 45px;
	border-radius: 50%;
}

input[type="range"]::-ms-thumb {
	width: 45px;
	height: 45px;
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
	width: 110%;
	position: absolute;
	top: 50%;
	transform: translate(-15px, -50%);
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
	background-color: var(--soft-cyan);
	width: 50%;
}

.slider-bar-wrapper .slider-control {
	background-color: var(--soft-cyan);
	border-radius: 50%;
	box-shadow: 0 10px 40px var(--soft-cyan);
	height: 40px;
	left: 0;
	position: absolute;
	top: 50%;
	transform: translate(-20px, -20px);
	width: 40px;
	z-index: 30;
}

input[type="range"]:active + button {
	background-color: var(--strong-cyan);
}
</style>
