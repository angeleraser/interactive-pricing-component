<template>
	<header class="header">
		<div class="bg-pattern-wrapper"></div>

		<div class="text">
			<h1>
				Simple, trafic based pricing
			</h1>

			<p>
				Sign up for our 30-day trial.
			</p>

			<p>No credit card required.</p>

			<svg class="pattern-circles" xmlns="http://www.w3.org/2000/svg" width="146" height="145">
				<g fill="none" fill-rule="evenodd" stroke="#CFD8EF">
					<circle cx="63" cy="82" r="62.5" />
					<circle cx="105" cy="41" r="40.5" />
				</g>
			</svg>
		</div>
	</header>
</template>

<script>
export default {
	name: "AppHeader",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
	align-items: center;
	display: flex;
	flex-direction: column;
	font-family: var(--ff-manrope);
	padding-top: 94px;
	position: relative;
	width: 100%;
}

.header .bg-pattern-wrapper {
	left: 0;
	overflow: hidden;
	position: absolute;
	top: 0;
	width: 100%;
	height: 450px;
	border-bottom-left-radius: 200px;
	background-color: var(--bg-pattern);
	z-index: -1;
}

.header .bg-pattern-wrapper img {
	max-width: fit-content;
}

.header .text {
	align-items: center;
	display: flex;
	flex-flow: column nowrap;
	text-align: center;
	position: relative;
	width: 90%;
}

.header .text > *:not(svg) {
	z-index: 10;
}

.header .text h1 {
	color: var(--dark-desaturated-blue);
	font-size: 24px;
	font-weight: 800;
	margin-bottom: 24px;
}

.header .text p {
	color: var(--grayish-blue);
	font-size: 15px;
	font-weight: 600;
}

.header .text p:first-of-type {
	margin-bottom: 12px;
}

.header .pattern-circles {
	position: absolute;
	top: 0;
	z-index: 5;
	transform: translate(0, -25%);
}

@media screen and (min-width: 480px) {
	.header .text {
		flex-flow: row wrap;
		justify-content: center;
	}

	.header .text h1 {
		width: 100%;
	}

	.header .text p:first-of-type {
		margin-bottom: 0;
		margin-right: 2px;
	}
}
</style>
