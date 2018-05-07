<!-- Router.vue -->
<template>
    <component :is="routedComponent"></component>
</template>

<script>

	import {listen} from './history'
	import HomePage from "./HomePage"
	import ArticlesPage from "./ArticlesPage"

	const routes = {
		"/": HomePage,
		"/articles": ArticlesPage
	};

	export default {
		data() {
			return {current: window.location.pathname}
		},
		computed: {
			routedComponent() {
				return routes[this.current]
			}
		},
		created() {
			listen((route, previousRoute) => {
				this.current = route
			})
			window.addEventListener(
				'popstate',
				event => (this.current = window.location.pathname)
			)
		}
	}
</script>