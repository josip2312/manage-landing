<template>
	<header class="header">
		<div class="wrapper container">
			<a class="logo" href="#">
				<img src="@/assets/images/logo.svg" alt="" />
			</a>
			<Navigation :isNavigationVisible="isNavigationVisible" />
			<button
				aria-label="Navigation toggle"
				class="nav-toggle"
				@click="toggleNavigation"
			>
				<transition name="fade" mode="out-in">
					<img
						key="open"
						v-show="!isNavigationVisible"
						src="@/assets/images/icon-hamburger.svg"
						alt=""
					/>
				</transition>
				<transition name="fade" mode="out-in">
					<img
						key="close"
						v-show="isNavigationVisible"
						src="@/assets/images/icon-close.svg"
						alt=""
					/>
				</transition>
			</button>
			<button class="btn">Get Started</button>
		</div>
	</header>
</template>

<script>
import { onMounted, ref } from "vue";

import Navigation from "./Navigation";
export default {
	name: "TheHeader",
	components: {
		Navigation,
	},
	setup() {
		let isNavigationVisible = ref(false);

		const toggleNavigation = () => {
			isNavigationVisible.value = !isNavigationVisible.value;
		};
		onMounted(() => {
			window.addEventListener("scroll", () => {
				const header = document.querySelector("header");
				header.classList.toggle("sticky", window.scrollY > 0);
			});
		});
		return { toggleNavigation, isNavigationVisible };
	},
};
</script>

<style lang="scss" scoped>
.fade-enter-from {
	opacity: 0;
}

.fade-enter-active {
	transition: opacity 200ms ease-in-out;
}
.fade-leave-active {
	opacity: 0;
}

header {
	position: fixed;
	top: 0;
	left: 0;
	right: 0;

	z-index: 2;
	transition: background-color 350ms ease-in-out;
}
.sticky {
	background-color: var(--white);
}
.wrapper {
	position: relative;
	display: flex;
	padding: 2rem 0;
	justify-content: space-between;

	.nav-toggle {
		border: none;
		background: none;

		cursor: pointer;
		img {
			width: 3rem;
		}
		@media only screen and(min-width:$v-10) {
			display: none;
		}
	}
	.nav-toggle:focus {
		outline: 1px solid var(--blue-400);
	}
	.logo {
		margin-top: 1rem;
		@media only screen and(min-width:$v-10) {
			margin-top: 0;
			align-self: center;
		}
		img {
			width: 12.5rem;
		}
	}
	.btn {
		display: none;
		align-self: center;
		@media only screen and(min-width:$v-10) {
			display: block;
		}
	}
}
</style>