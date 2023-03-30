<script setup>
import starActive from '../assets/star-active.svg'
import starInactive from '../assets/star-inactive.svg'
const range = [1, 2, 3, 4, 5]
defineProps({
    rating: String
})
</script>

<template>
    <div class="rates">
        <img class="rate" v-for="rate in range" :src="rating < rate ? starInactive : starActive" />
    </div>
</template>

<style>
.rates {
    margin-top: 20px;
    gap: 0;
}

.rate {
    width: 36px;
    height: 36px;
}
</style>
