<template>
    <section>
        <div class="alert alert-danger mb-3" v-if="$route.query.message">
            Need login first
        </div>
        <form @submit.prevent="onSubmit">
            <h1>Login page</h1>
            <div class="form-group">
                <input class="form-control" type="text">
            </div>

            <p>
                <NuxtLink to="/">To home page</NuxtLink>
            </p>

            <button class="btn btn-primary" type="submit">
                login
            </button>
        </form>
    </section>
</template>

<script>
export default {
    layout: 'empty',
    methods: {
        onSubmit() {
            this.$store.dispatch('login')
            this.$router.push('/')
        }
    }
}
</script>

<style scoped>
    form{
        width: 500px;
        margin: 0 auto;
    }
</style>