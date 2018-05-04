<!-- Router.vue -->
<template>
    <component :is="routedComponent"></component>
</template>

<script>
	import HomePage from "./HomePage";
	import ArticlesPage from "./ArticlesPage";

	const routes = {
		"/": HomePage,
		"/articles": ArticlesPage
	};

	export default {
		data() {
			return { current: window.location.pathname };
		},
		computed: {
			routedComponent() {
				return routes[this.current];
			}
		}
	};
</script>