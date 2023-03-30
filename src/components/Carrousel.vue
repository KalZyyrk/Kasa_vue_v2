
<script>
import CarouselArrow from '../assets/CarouselArrow.svg'
export default {
    data() {
        return {
            indexPicture: 0,
            CarouselArrow
        }
    },
    props: {
        images: Array
    },
    methods: {
        previousPict() {
            if (this.indexPicture <= 0) {
                this.indexPicture = this.images.length - 1
            } else {
                this.indexPicture--
            }
        },
        nextPict() {
            if (this.indexPicture >= this.images.length - 1) {
                this.indexPicture = 0
            } else {
                this.indexPicture++
            }
        }
    },
    computed: {
        UniquePic() {
            if (this.images.length <= 1) {
                return true
            } else {
                return false
            }
        }
    }

}
</script>

<template>
    <div class="carousel">
        <img class="arrowCar left" :src="CarouselArrow" @click="previousPict" :class="UniquePic ? 'hidden' : ''">
        <img class="arrowCar right" :src="CarouselArrow" @click="nextPict" :class="UniquePic ? 'hidden' : ''">
        <p class="carouselIndex" :class="UniquePic ? 'hidden' : ''">{{ indexPicture + 1 }}/{{ images.length }}</p>
        <img class="picture" :src="images[indexPicture]" alt="picture of the lodging">
    </div>
</template>

<style>
.carousel {
    position: relative;
    overflow: hidden;
    width: 100%;
    border-radius: 25px;
    height: 415px;
    display: flex;
}

.picture {
    z-index: 0;
    width: 100%;
    object-fit: cover;
    align-self: center;
}

.arrowCar {
    position: absolute;
    z-index: 5;
    top: 45%;
}

.hidden {
    display: none;
}

.left {
    left: 10px;
}

.right {
    rotate: 180deg;
    right: 10px;
}

.carouselIndex {
    color: white;
    font-weight: 500;
    font-size: 18px;
    position: absolute;
    z-index: 5;
    bottom: 10px;
    left: 50%;
}
</style>