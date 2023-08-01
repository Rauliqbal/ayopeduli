<script setup>
const { data: item } = await useFetch("https://donasi-open-api.ricky-sanjaya.my.id/api/slider");
</script>
<template>
   <Swiper
      :modules="[SwiperPagination]"
      :slides-per-view="1"
      :spaceBetween="30"
      :loop="true"
      :autoplay="{
         delay: 8000,
         disableOnInteraction: true,
      }"
      :pagination="{
         dynamicBullets: true,
      }"
   >
      <SwiperSlide class="pb-10" v-for="item in item.data" :key="item">
         <img class="w-full h-[60vh] object-cover rounded-2xl" :src="item.image" alt="" />
      </SwiperSlide>
   </Swiper>
</template>
