<script setup>
defineProps({
    title: String,
    contents: Array,
    content: String
    })
</script>

<script>
export default {
    data() {
        return {
            isActive: false,
        }
    },
    methods: {
        setActive() {
            this.isActive = !this.isActive
        }
    }
}
</script>

<template>
    <div class="drop-down">
        <div class="drop-down-btn" @click="setActive">
            <h2>{{ title }}</h2>
            <img src="@/assets/arrow.svg" class="arrow" :class="isActive ? 'arrow-up' : 'arrow-down'">
        </div>
        <div class="drop-down-text" :class="isActive ? 'active' : 'close'">
            <p v-if="content">{{ content }}</p>
            <ul v-if="contents"><li v-for="line in contents">{{ line }}</li></ul>
        </div>
    </div>
</template>

<style>
    .drop-down {
        margin: 0;
    }
    .drop-down-btn {
        display: flex;
        background-color: var(--orange);
        border-radius: 10px;
        padding: 13px 20px;
        position: relative;
        align-items: center;
        cursor: pointer;
    }
    .drop-down-btn h2 {
        font-size: 18px;
        font-weight: 500;
        color: white;
    }
    .arrow {
        position: absolute;
        right: 10px;

    }
    .drop-down-text {
        margin-top: -15px;
        background-color: #F6F6F6;
        padding: 40px 20px 27px;
        border-radius: 10px;
        z-index: -1;
    }
    .drop-down-text p, .drop-down-text li  {
        color: var(--orange);
        font-size: 18px;
        font-weight: 500;
        list-style: none;
    }
    .close  {
        display: none;
    }
    .arrow-down{
        rotate: 180deg;
    }
</style>