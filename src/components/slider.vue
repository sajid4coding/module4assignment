<script setup>
    import { ref } from 'vue';
    const activeImage = ref('https://images.pexels.com/photos/120049/pexels-photo-120049.jpeg?cs=srgb&dl=pexels-mike-bird-120049.jpg&fm=jpg')
    const sliderImages = [
        {id:1, aria_label:"slide 1", image:"https://images.pexels.com/photos/120049/pexels-photo-120049.jpeg?cs=srgb&dl=pexels-mike-bird-120049.jpg&fm=jpg"},
        {id:2, aria_label:"slide 2", image:"https://t4.ftcdn.net/jpg/05/52/39/55/360_F_552395539_Zt0bAFvm8aCQlQTuI2JdCEogW7piLYza.jpg"},
        {id:3, aria_label:"slide 3", image:"https://i.pinimg.com/736x/31/0c/3e/310c3ec33b5bad57791c43219814ad12.jpg"},
        {id:4, aria_label:"slide 4", image:"https://img3.wallspic.com/attachments/originals/5/3/2/4/34235-mercedes_benz_sls_amg-car-mercedes_benz_s_class-mercedes_benz_cls_class-wheel-4096x2160.jpg"}
    ]
    function changeImage(sliderImage){
        activeImage.value = sliderImage.image
    }
</script>
<template>
    <div class="container my-5">
        <h1 class="text-center">Vue 3 Slider</h1>
        <div class="border border-primary border border-5">
            <div id="carouselExampleIndicators" class="carousel slide" data-bs-ride="carousel">
                <div class="carousel-indicators">
                    <button @click="changeImage(sliderImage)" v-for="sliderImage in sliderImages" :key="aria_label" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide-to="0" class="active" aria-current="true" :aria-label="sliderImage.aria_label"></button>
                </div>
                <div class="carousel-inner">
                    <div class="carousel-item active">
                        <img :src="activeImage" class="d-block w-100" alt="...">
                    </div>
                </div>
                <!-- <button @click="changeImage(sliderImage)" v-for="sliderImage in sliderImages" :key="id" class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="prev">
                    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Previous</span>
                </button>
                <button @click="changeImage(sliderImage)" v-for="sliderImage in sliderImages" :key="id" class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators" data-bs-slide="next">
                    <span class="carousel-control-next-icon" aria-hidden="true"></span>
                    <span class="visually-hidden">Next</span>
                </button> -->
            </div>
        </div>
    </div>
</template>
<style scoped>
.container{
    width: 50%;
}
</style>
