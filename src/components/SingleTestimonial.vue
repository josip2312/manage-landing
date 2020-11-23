<template>
	<div
		class="testimonial spacing"
		:class="{
			active: testimonial.active,
		}"
	>
		<img class="testimonial-image" :src="testimonial.imgSrc" alt="" />
		<div class="testimonial-name">
			{{ testimonial.name }}
		</div>
		<p class="testimonial-paragraph">
			{{ testimonial.paragraph }}
		</p>
	</div>
</template>

<script>
export default {
	name: "SingleTestimonial",
	props: {
		testimonial: {
			type: Object,
			required: true,
		},
	},
};
</script>

<style lang="scss" scoped>
.testimonial {
	flex: 1;
	position: absolute;
	display: flex;
	flex-direction: column;
	align-items: center;

	opacity: 0;
	transition: opacity 400ms ease-in-out;

	@media only screen and(min-width:$v-12) {
		position: relative;
	}
	&-name {
		font-weight: 600;
		font-size: 1.8rem;
	}
	&-paragraph {
		max-width: 45rem;
		color: var(--blue-text);
	}
}
.testimonial.active {
	opacity: 1;
}
</style>