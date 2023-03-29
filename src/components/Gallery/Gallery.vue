<script setup>
import datas from '../../datas/data.json'
import GalleryCard from './GalleryCard.vue';
</script>

<template>
    <div class="gallery">
        <div v-for="data in datas" >
            <GalleryCard :lodging="data"  />
        </div>
    </div>
</template>

<style>
    .gallery {
        display: flex;
        flex-wrap: wrap;
        margin: 40px 0;
        gap: 50px 60px;
        padding: 56px 50px;
        background-color: #F6F6F6;
        border-radius: 25px;
    }

    @media screen and (max-width: 580px) {
        .gallery {
            flex-direction: column;
            padding: 0;
            background: none;
        }
    }
</style>