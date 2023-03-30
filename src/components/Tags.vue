<script setup>
defineProps({
    tags: Array
})
</script>

<template>
    <div class="tags">
        <div v-for="tag in tags" class="tag"> {{ tag }}</div>
    </div>
</template>

<style>
.tags {
    display: flex;
    gap: 10px;
    align-items: center;
    margin-top: 20px;
}

.tag {
    display: flex;
    background-color: var(--orange);
    color: white;
    border-radius: 10px;
    height: 25px;
    min-width: 115px;
    font-size: 14px;
    font-weight: 500;
    justify-content: center;
    align-items: center;
}
</style>