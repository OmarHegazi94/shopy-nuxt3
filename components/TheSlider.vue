<script lang="ts" setup>
// For controls
// const slider = useSwiper();

const slides = ref([
  {
    img_url: "https://api.a2zmegastore.com/storage/sliders/2023/11/1701067202_01.jpg",
    img_alt: "games",
  },
  {
    img_url: "https://api.a2zmegastore.com/storage/sliders/2023/11/1701124670_03.png",
    img_alt: "games2",
  },
  {
    img_url: "https://api.a2zmegastore.com/storage/sliders/2023/11/1701124754_02.png",
    img_alt: "games3",
  },
]);
</script>

<template>
  <div class="slider-container">
    <Swiper
      :height="300"
      :modules="[SwiperAutoplay, SwiperEffectCreative, SwiperController, SwiperPagination]"
      :slides-per-view="1"
      :loop="true"
      :effect="'creative'"
      :autoplay="{
        delay: 8000,
        disableOnInteraction: true,
      }"
      :creative-effect="{
        prev: {
          shadow: false,
          translate: ['0%', 0, -1],
        },
        next: {
          translate: ['100%', 0, 0],
        },
      }"
      :pagination="{clickable: true}"
    >
      <SwiperSlide v-for="(slide, index) in slides" :key="index">
        <img :src="slide.img_url" :alt="slide.img_alt" class="slider-img" />
      </SwiperSlide>

      <!-- <button @click="slider.slideNext()">Next</button>
      <button @click="slider.slidePrev()">Previous</button> -->
    </Swiper>
  </div>
</template>

<style>
.slider-container {
  max-width: 1280px;
  margin: 5rem auto;
}

.swiper {
  height: 425px;
}
.swiper-slide {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 18px;
  height: 400px;
  font-size: 4rem;
  font-weight: bold;
  font-family: "Roboto", sans-serif;
  border-radius: 8px;
}
.swiper-wrapper {
  /* min-width: 100vh;
  width: 100vh; */
  /* padding: 4rem; */
}
.swiper-cards {
  width: 240px;
  height: 240px;
}
.swiper-cards .swiper-slide {
  border-radius: 6px;
  border: 1px solid black;
}
.slider-img {
  max-width: 100%;
  height: 100%;
  border-radius: 8px;
  object-fit: cover;
}

.swiper-pagination {
  bottom: 0px !important;
}

.swiper-pagination-bullet {
  width: 10px;
  height: 10px;
  background-color: #fff;
  border: 1px solid blue;
}

.swiper-pagination-bullet-active {
  background-color: blue;
}
</style>
