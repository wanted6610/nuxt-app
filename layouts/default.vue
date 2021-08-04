<template>
<div class="container">
    <Navbar />

    <main>
        <div>
            <Nuxt />
        </div>
    </main>
</div>

</template>

<script>
import Navbar from '@/components/Navbar'
export default {
    components: {
        Navbar
    },
    layout: 'default'
}