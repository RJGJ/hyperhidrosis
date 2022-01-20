<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination } from 'swiper';

import 'swiper/css/navigation';


</script>

<template>
  <swiper
    ref="mySwiper"
    class="swiper-before-after"
    direction="horizontal"
    :loop="true"
    :autoplay="{ delay: 3000 }"
    :pagination="{ clickable: true }"
    :space-between="30"
    :breakpoints="{ 1200: {}, 576: { spaceBetween: 70 } }"
    loop
    :modules="[Pagination]"
  >
    <swiper-slide v-for="  i in [...Array(58).keys()]" :key="i">
      <div class="container p-0">
        <img loading="lazy" :src="`assets/img/before-after/${i + 1}.webp`" class="img-fluid" />
      </div>
    </swiper-slide>
  </swiper>
</template>