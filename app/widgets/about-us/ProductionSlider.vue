<template>
    <section class="gallery-page">
        <div class="container gallery-page__container-bg">
            <div class="gallery-page__overlay"></div>

            <div class="gallery-page__header">
            <h6 class="gallery-page__subtitle">Галерея:</h6>
            <div class="gallery-page__main">
                <h3 class="gallery-page__title">Наше производство</h3>
                <p class="gallery-page__text">
                Производственный процесс в действии. Работаем с вниманием к каждой детали.
            </p>
            </div>
            
            </div>

            <div class="gallery-page__content">
            <Swiper
                :slides-per-view="3"
                :space-between="20"
                :navigation="true"
                class="gallery-slider"
            >
                <SwiperSlide v-for="(img, index) in images" :key="index">
                <img :src="img" alt="gallery item" class="gallery-slide__img" />
                </SwiperSlide>
            </Swiper>

            
            </div>
        </div>
    </section>

</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';

const images = [
  '/images/aboutUs-slider/slide1.png',
  '/images/aboutUs-slider/slide2.png',
  '/images/aboutUs-slider/slide3.png',
  '/images/aboutUs-slider/slide4.png'
];
</script>

<style lang="scss" scoped>



.gallery-page {
    position: relative;
    margin-top: 100px;

  &__container-bg {
    position: relative;
    padding: 40px;
    background-image: url('./images/bg-productSlider.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
   
  }

  &__overlay {
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.5);
    z-index: 1;
    border-radius: inherit;
  }

  .gallery-page__header,
  .gallery-page__content {
    position: relative;
    z-index: 2;
  }

  &__header {
    margin-top: 68px;
  }

  &__subtitle {
    @include headline6;
  }
  &__main{
    display: flex;
    align-items: center;
    gap:407px;
    
    
  }
  &__title {
    @include headline3;
   
  }

  &__text {
    @include text3;
    
    
  }
  &__content {
    margin-top: 60px;
  }

  


}

</style>
