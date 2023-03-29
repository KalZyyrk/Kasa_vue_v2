<script setup>
defineProps({
    lodging: Object,
})
</script>

<template>
    <RouterLink :to="lodging.id">
        <div class="card">
            <img :src="lodging.cover" alt="">
            <h2>{{ lodging.title }}</h2>
        </div>
    </RouterLink>
</template>

<style>
    .card {
        height: 340px;
        width: 340px;
        overflow: hidden;
        display: flex;
        position: relative;
        border-radius: 10px;
    }
    .card h2 {
        z-index: 5;
        font-size: 18px;
        font-weight: 500;
        color: white;
        position: absolute;
        bottom: 20px;
        left: 20px;
    }
    .card img {
        height: 100%;
        filter: brightness(0.7);
    }

    @media screen and (max-width: 580px) {
        .card {
            margin: auto;
        }
    }
</style>