<template>
    <div>
        <button @click="goTo('/articles')">Go to Articles</button>
        <button @click="goTo('/')">Go to Home</button>
        <app-router></app-router>
    </div>
</template>

<script>
    import AppRouter from './AppRouter'

    export default {
        components: {
            AppRouter
        },
        methods: {
            goTo(route) {
                window.location = route
            }
        }
    }
</script>