<template>
	<section id="cta">
		<div class="container spacing-lg">
			<h2 class="heading-2">Simplify how your team works today.</h2>
			<button class="btn btn-sec">Get started</button>

			<img
				class="watermark"
				src="@/assets/images/bg-simplify-section-mobile.svg"
				alt=""
			/>
		</div>
	</section>
</template>

<script>
export default {
	name: "AppCtaSection",
};
</script>

<style lang="scss" scoped>
@import "@/assets/sass/_variables";

#cta {
	position: relative;
	background-color: var(--accent);
	padding: 7.5em 0;
}
.heading-2 {
	color: var(--grey);
	font-size: 4.5rem;
	max-width: 60rem;

	@media only screen and(min-width:$v-12) {
		text-align: left;
	}
}
.container {
	display: flex;
	flex-direction: column;
	align-items: center;
	text-align: center;
	@media only screen and(min-width:$v-12) {
		flex-direction: row;
		justify-content: space-between;
	}
}
.watermark {
	position: absolute;
	left: 0;
	top: 50%;
	transform: translateY(-50%);
}
</style>