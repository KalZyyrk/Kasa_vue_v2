<script setup>
import Banner from '../components/Banner.vue';
import Gallery from '../components/Gallery/Gallery.vue';
</script>

<template>
  <main>
    <Banner msg="Chez vous, partout et ailleurs" image="home"/>
    <Gallery />
  </main>
</template>

<style>
  main {
    margin-top: 63px;
  }

  @media screen and (max-width: 580px) {
    main
      { 
       margin-top: 16px;
      }
  }
</style>