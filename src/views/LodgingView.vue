

<script>
import data from "@/datas/data.json";
import Carrousel from "../components/Carrousel.vue";
import DropDown from "../components/DropDown.vue";
import Rates from "../components/Rates.vue";
import Tags from '../components/Tags.vue'

export default {
    computed: {
        lodgingId() {
            return this.$route.params.logementId;
        },
        lodging() {
            return data.find(lodging => lodging.id === this.lodgingId);
        }
    },
    components: { DropDown, Tags, Rates, Carrousel }
}
</script>

<template>
    <main>
        <div class="lodgingImg">
            <Carrousel :images="lodging.pictures" />
        </div>
        <div class="lodgingDesc">
            <div class="lodgingInfo">
                <h1>{{ lodging.title }}</h1>
                <h2>{{ lodging.location }}</h2>
                <Tags :tags="lodging.tags" />
            </div>
            <div>
                <div class="hostInfo">
                    <h2>{{ lodging.host.name }}</h2>
                    <img class="hostImg" :src="lodging.host.picture" alt="photo de l'hote">
                </div>
                <Rates :rating="lodging.rating" />
            </div>
        </div>
        <div class="lodgingDrop">
            <DropDown class="dropDown" title="Description" :content="lodging.description" />
            <DropDown class="dropDown" title="Équipements" :contents="lodging.equipments" />
        </div>
    </main>
</template>

<style>
.lodgingDrop {
    display: flex;
    justify-content: space-between;
    gap: 76px;
}

.dropDown {
    margin-top: 24px;
    width: 50%;
    margin-bottom: 40px;
}

.lodgingDesc {
    margin-top: 30px;
    display: flex;
    justify-content: space-between;
    color: var(--orange);
}

.lodgingInfo h1 {
    font-size: 36px;
    font-weight: 500;
}

.lodgingInfo h2 {
    font-size: 18px;
    font-weight: 500;
}

.hostInfo {
    display: flex;
    gap: 10px;
}

.hostInfo h2 {
    font-size: 18px;
    font-weight: 500;
    text-align: right;
    width: 93px;
}

.hostImg {
    border-radius: 50%;
    object-fit: cover;
    width: 64px;
}
</style>