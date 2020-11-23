<template>
	<nav class="nav" :class="{ active: isNavigationVisible }">
		<a href="#pricing" class="nav-link">Pricing</a>
		<a href="#product" class="nav-link">Product</a>
		<a href="#about" class="nav-link"> About Us</a>
		<a href="#careers" class="nav-link"> Careers</a>
		<a href="#community" class="nav-link"> Community</a>
	</nav>
</template>

<script>
export default {
	name: "Navigation",
	props: {
		isNavigationVisible: {
			type: Boolean,
			required: true,
		},
	},
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped>
.nav {
	position: absolute;
	top: 7.5rem;
	left: 0;
	right: 0;

	padding: 2.5rem 1rem;
	box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
	background-color: var(--white);
	display: flex;
	flex-direction: column;
	align-items: center;

	opacity: 0;
	pointer-events: none;
	transition: opacity 250ms ease-in-out;
	z-index: 10;

	@media only screen and(min-width:$v-10) {
		position: relative;
		flex-direction: row;
		top: 0;
		opacity: 1;
		pointer-events: all;
		background: none;
		box-shadow: none;
		padding: 0;
	}

	.nav-link {
		font-weight: 600;
		font-size: 1.8rem;
		padding: 1rem 0.5rem;
		@media only screen and(min-width:$v-10) {
			font-weight: 400;
			font-size: 1.6rem;
			padding: 1rem 1rem;
		}
		@media only screen and(min-width:$v-12) {
			padding: 1rem 2rem;
		}
	}
	.nav-link:focus {
		outline: 1px solid var(--blue-400);
	}
	.nav-link:hover {
		opacity: 0.8;
	}
}
.nav.active {
	opacity: 1;
	pointer-events: all;
}
</style>