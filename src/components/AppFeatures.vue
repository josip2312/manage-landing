<template>
	<section id="features" class="features">
		<div class="container spacing">
			<div class="features-heading spacing">
				<h2 class="heading-2">What’s different about Manage?</h2>
				<p class="features-paragraph">
					Manage provides all the functionality your team needs,
					without the complexity. Our software is tailor-made for
					modern digital product teams.
				</p>
			</div>
			<div class="features-items spacing-xl">
				<SingleFeature
					v-for="feature in features"
					:key="feature.buttonText"
					:feature="feature"
				/>
			</div>
		</div>
	</section>
</template>

<script>
import SingleFeature from "./SingleFeature";
export default {
	name: "AppFeatures",
	components: {
		SingleFeature,
	},
	data() {
		return {
			features: [
				{
					buttonText: "01",
					title: "Track company-wide progress",
					paragraph:
						"See how your day-to-day tasks fit into the wider vision.Go from tracking progress at the milestone level all theway done to the smallest of details. Never lose sight of the bigger picture again.",
				},
				{
					buttonText: "02",
					title: "Advanced built-in reports",
					paragraph:
						"Advanced built-in reports Set internal delivery estimates and track progress toward company goals. Our customisable dashboard helps you build out the reports you need to keep key stakeholders informed.",
				},
				{
					buttonText: "03",
					title: "Everything you need in one place",
					paragraph:
						"Everything you need in one place Stop jumping from one service to another to communicate, store files, track tasks and share documents. Manage offers an all-in-one team productivity solution.",
				},
			],
		};
	},
};
</script>

<style lang="scss" scoped>
@import "@/assets/sass/_variables";

.features {
	background-image: url(../assets/images/bg-tablet-pattern.svg);
	background-origin: border-box;
	background-repeat: no-repeat;
	background-position: -50% 50%;

	@media only screen and(min-width:$v-12) {
		background-position: -50% -50%;
	}
}
.container {
	display: flex;
	flex-direction: column;
	align-items: center;
	@media only screen and(min-width:$v-12) {
		flex-direction: row;
		justify-content: space-between;
		align-items: flex-start;
	}
}
.features-heading {
	padding: 2.5rem 0;
	text-align: center;
	margin-bottom: 5rem;
	@media only screen and(min-width:$v-12) {
		text-align: left;
	}

	.heading-2 {
		max-width: 35rem;
		margin-left: auto;
		margin-right: auto;
		@media only screen and(min-width:$v-12) {
			margin-left: 0;
		}
	}

	.features-paragraph {
		width: 90%;
		max-width: 45rem;
		margin-left: auto;
		margin-right: auto;

		color: var(--blue-text);
		@media only screen and(min-width:$v-12) {
			margin-left: 0;
		}
	}
}
.features-items {
	display: flex;
	flex-direction: column;
	align-items: center;
}
</style>