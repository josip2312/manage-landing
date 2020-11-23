<template>
	<section id="showcase" class="showcase">
		<div class="container">
			<div class="showcase-image">
				<img src="@/assets/images/illustration-intro.svg" alt="" />
			</div>
			<div class="showcase-heading spacing-lg">
				<h1 class="heading-1">
					Bring everyone together to build better products.
				</h1>
				<p class="showcase-paragraph">
					Manage makes it simple for software teams to plan day-to-day
					tasks while keeping the larger team goals in view.
				</p>
				<button class="btn">Get started</button>
			</div>
		</div>
	</section>
</template>

<script>
export default {
	name: "AppShowcase",
};
</script>

<style lang="scss" scoped>
.showcase {
	min-height: 91vh;
	display: flex;
	justify-content: flex-start;
	background-image: url(../assets/images/bg-tablet-pattern.svg);
	background-origin: border-box;
	background-repeat: no-repeat;
	background-position: 50% -200%;

	@media only screen and(min-width:$v-12) {
		background-position: 115% -200%;
	}
}
.container {
	padding: 5em 0;
	display: flex;
	flex-direction: column;
	align-items: center;
	@media only screen and(min-width:$v-12) {
		flex-direction: row-reverse;
		justify-content: space-between;
	}
}

.showcase-image {
	img {
		@media only screen and(min-width:$v-12) {
			transform: scale(1.15);
		}
	}
}

.showcase-heading {
	padding: 2.5rem 0;
	max-width: 60rem;
	text-align: center;

	@media only screen and(min-width:$v-12) {
		max-width: 50rem;
		text-align: left;
	}

	.showcase-paragraph {
		max-width: 80%;
		margin-left: auto;
		margin-right: auto;
		font-size: 1.8rem;
		color: var(--blue-text);
		@media only screen and(min-width:$v-12) {
			margin-left: 0;
		}
	}
}
</style>