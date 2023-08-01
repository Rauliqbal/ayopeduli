<script setup>
const { data: categorys } = await useFetch("https://donasi-open-api.ricky-sanjaya.my.id/api/category");
</script>
<template>
   <section>
      <div class="shadow-xl rounded-2xl bg-white px-8 py-6">
         <h2 class="text-2xl font-bold">AyoPeduli kepada mereka yang membutuhkan</h2>
         <p class="text-slate-500 mt-2 text-lg">Pilih Kategori favorit kamu</p>
         <div class="grid grid-cols-2 md:grid-cols-4 justify-items-center mt-8">
            <div v-for="category in categorys.data.data" :key="category" class="flex items-center flex-col">
               <div class="w-28 h-28 flex items-center justify-between bg-white ring-2 ring-slate-300 rounded-full">
                  <NuxtLink to="/"><img class="p-5" :src="category.image" alt="" /></NuxtLink>
               </div>
               <h5 class="mt-2 font-bold text-lg">{{ category.name }}</h5>
            </div>
         </div>
      </div>
   </section>
</template>
