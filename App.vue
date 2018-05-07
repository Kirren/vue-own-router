<template>
    <div>
        <button @click="goTo('/articles')">Go to Articles</button>
        <button @click="goTo('/')">Go to Home</button>
        <app-router></app-router>
    </div>
</template>

<script>
    import Router from './Router'
    import { push } from './history'

    export default {
        components: {
            Router
        },
        methods: {
            goTo(route) {
                // 1. window.location = route
                // 2. history.pushState(null, null, route)
                push(route)
            }
        }
    }
</script>