<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <a class="navbar-brand" href="#">Nuxt SSR</a>

        <div class="collapse navbar-collapse">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <NuxtLink exact active-class="active" class="nav-link" to="/">Home</NuxtLink>
                </li>
                <li class="nav-item">
                    <NuxtLink active-class="active" class="nav-link" to="/about">About</NuxtLink>
                </li>               
                <li class="nav-item">
                    <NuxtLink active-class="active" class="nav-link" to="/users">Users</NuxtLink>
                </li>                     
                <li class="nav-item" v-if="!hasToken">
                    <NuxtLink active-class="active" class="nav-link" to="/login">Login</NuxtLink>
                </li>          
                <li class="nav-item" v-else>
                    <a class="nav-link" @click.prevent="logout" href="#">Logout</a>
                </li>                                
            </ul>
        </div>
    </nav>
</template>

<script>
export default {
    computed: {
        hasToken() {
            return this.$store.getters.hasToken
        }
    },
    methods: {
        logout() {
            this.$store.dispatch('logout')
            this.$router.push('/login')
        }
    }
}
</script>