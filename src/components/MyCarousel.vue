<script setup lang="ts">
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';
</script>

<template>
  <carousel>
    <slide v-for="slide in 10" :key="slide">
      <div class="carousel__item">
        <h2>Slide {{ slide }}</h2>
      </div>
    </slide>

    <template #addons>
      <navigation />
      <pagination />
    </template>
  </carousel>
</template>
