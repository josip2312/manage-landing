<template>
	<TheHeader />
	<AppShowcase />
	<AppFeatures />
	<AppTestimonials />
	<AppCtaSection />
	<TheFooter />
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import TheFooter from "./components/TheFooter.vue";
import AppShowcase from "@/components/AppShowcase";
import AppFeatures from "@/components/AppFeatures";
import AppTestimonials from "@/components/AppTestimonials";
import AppCtaSection from "@/components/AppCtaSection";
export default {
	name: "App",
	components: {
		TheHeader,
		AppShowcase,
		AppFeatures,
		AppTestimonials,
		AppCtaSection,
		TheFooter,
	},
};
</script>

<style lang="scss">
//@import "@/assets/sass/app.scss";
</style>
