<template>
	<article class="pricing-card">
		<section class="pricing-card__pricing">
			<!-- Page views count -->
			<div class="pricing-card__page-views-count">{{ `100K` }} Pageviews</div>

			<!-- Slider input range  -->
			<slider-bar :classNames="`input-range`" />

			<!-- Pricing -->
			<div class="pricing-card__calculated-price">
				<span class="pricing">$16.00</span>
				<span class="based">/ month</span>
			</div>

			<!-- Toggle pricing based time -->
			<div class="pricing-card__toggle-based-time">
				<p class="pricing-card__toggle-based-time__time">Monthly Billing</p>

				<pricing-toggle />

				<p class="pricing-card__toggle-based-time__time">
					Yearly Billing
					<span class="time-discount">-25% <span> discount</span></span>
				</p>
			</div>
		</section>

		<section class="pricing-card__info">
			<ul>
				<li>Unlimited websites</li>
				<li>100% data ownership</li>
				<li>Email reports</li>
			</ul>

			<button class="pricing-card__star-trial-button">Star my trial</button>
		</section>
	</article>
</template>

<script>
import PricingToggle from "./PricingToggle.vue";
import SliderBar from "./SliderBar.vue";
export default {
	components: { SliderBar, PricingToggle },
	name: "PricingCard",
};
</script>

<style scoped>
.pricing-card {
	align-self: center;
	background-color: var(--white);
	border-radius: 8px;
	box-shadow: 0 -2px 22px rgba(0, 0, 0, 0.1);
	display: flex;
	flex-direction: column;
	font-family: var(--ff-manrope);
	max-width: 538px;
	margin: 72px 0;
	width: 90%;
	z-index: 30;
}

.pricing-card__pricing {
	align-items: center;
	border-bottom: 1px solid var(--light-grayish-blue-1);
	display: flex;
	flex-direction: column;
	padding: 40px 24px 36px;
	width: 100%;
}

.pricing-card .input-range {
	width: 85%;
	margin: 32px 0;
}

.pricing-card__page-views-count {
	color: var(--grayish-blue);
	font-size: 14px;
	font-weight: 800;
	letter-spacing: 2px;
	text-transform: uppercase;
}

.pricing-card__calculated-price {
	display: flex;
	align-items: center;
}

.pricing-card__calculated-price .pricing {
	color: var(--dark-desaturated-blue);
	font-size: 36px;
	font-weight: 800;
}

.pricing-card__calculated-price .based {
	color: var(--grayish-blue);
	font-size: 16px;
	font-weight: 600;
	margin-left: 4px;
}

.pricing-card__info {
	align-items: center;
	display: flex;
	flex-direction: column;
	padding: 32px 46px;
}

.pricing-card__info ul {
	align-items: center;
	display: flex;
	flex-direction: column;
	list-style: url("../assets/svg/icon-check.svg");
	width: 100%;
}

.pricing-card__info ul li {
	color: var(--grayish-blue);
	font-size: 15px;
	font-weight: 600;
}

.pricing-card__info ul li:not(:last-child) {
	margin-bottom: 16px;
}

.pricing-card__star-trial-button {
	background-color: var(--dark-desaturated-blue);
	border-radius: 40px;
	color: var(--white);
	font-weight: 600;
	margin-top: 36px;
	padding: 16px 44px;
	flex-shrink: 0;
}

.pricing-card__toggle-based-time {
	display: flex;
	align-items: center;
	justify-content: center;
	margin-top: 42px;
	width: 100%;
}

.pricing-card__toggle-based-time__time {
	font-size: 12px;
	font-weight: 600;
	color: var(--grayish-blue);
}

.pricing-card__toggle-based-time .pricing-toggle-button {
	margin: 0 14px;
}

.pricing-card__toggle-based-time .time-discount {
	display: inline-flex;
	border-radius: 40px;
	padding: 4px 6px;
	font-size: 12px;
	background-color: var(--light-grayish-red);
	font-weight: 800;
	margin-left: 4px;
	color: var(--light-red);
}

.pricing-card__toggle-based-time .time-discount span {
	margin-left: 2px;
	display: none;
}

@media screen and (min-width: 600px) {
	.pricing-card__info {
		flex-direction: row;
		padding: 36px 48px;
	}

	.pricing-card__info ul {
		align-items: flex-start;
	}

	.pricing-card__star-trial-button {
		margin-top: 0;
	}

	.pricing-card__toggle-based-time .time-discount span {
		display: inline;
	}

	.pricing-card__toggle-based-time__time {
		font-size: 14px;
	}
}
</style>
