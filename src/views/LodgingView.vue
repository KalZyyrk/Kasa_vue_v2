

<script>
    import data from "@/datas/data.json"
import DropDown from "../components/DropDown.vue";
import Tags from "../components/Tags.vue"

    export default {
    computed: {
        lodgingId() {
            return this.$route.params.logementId;
        },
        lodging() {
            return data.find(lodging => lodging.id === this.lodgingId);
        }
    },
    components: { DropDown }
}
</script>

<template>
    <main>
        <div class="lodgingImg">
            <img :src="lodging.pictures[0]" alt="">
        </div>
        <div class="lodgingDesc">
            <div class="lodgingInfo">
                <h1>{{ lodging.title }}</h1>
                <h2>{{ lodging.location }}</h2>
                <Tags />
            </div>
            <div class="hostInfo"></div>
        </div>  
        <div class="lodgingDrop">
            <DropDown class="dropDown" title="Description" :content="lodging.description"/>
            <DropDown class="dropDown" title="Équipements" :contents="lodging.equipments"/>
        </div>
    </main>
</template>

<style>
    .lodgingDrop {
        display: flex;
        justify-content: space-between;
        gap: 76px;
    }
    .dropDown{
        width: 50%;
        margin-bottom: 40px;
    }
</style>