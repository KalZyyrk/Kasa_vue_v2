<script setup>
import homeImg from '@/assets/homeImg.jpg'
import aboutImg from '@/assets/aboutImg.jpg'
defineProps({
  msg: {
    type: String,
    required: true
  },
  image: String
})
</script>

<template>
    <div class="banner">
        <img :src="image === 'home' ? homeImg : aboutImg " />
        <h2>{{ msg }}</h2>
    </div>
</template>

<style>
    .banner {
        height: 223px;
        overflow: hidden;
        border-radius: 25px;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .banner img {
        width: 100%;
        object-fit: cover;
        filter: brightness(0.7);
    }
    .banner h2 {
        position: absolute;
        font-size: 48px;
        font-weight: 500;
        color: white;
        z-index: 5;
    }

    @media screen and (max-width: 580px) {
        .banner {
            height: 111px;
        }
        .banner h2 {
            text-align: left;
            padding: 16px;
            font-size: 22px;
            width: 240px;
        }
    }
</style>