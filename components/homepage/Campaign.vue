<script setup>
const { data: items } = await useFetch("https://donasi-open-api.ricky-sanjaya.my.id/api/campaign");
</script>
<template>
   <section>
      <div class="grid grid-cols-3">
         <div class="flex flex-col bg-white p-4 rounded-xl" v-for="item in items.data.data" :key="item">
            <img class="object-cover rounded-lg h-56" :src="item.image" alt="" />
            <div class="flex flex-col mt-4">
               <h4 class="font-medium text-xl">{{ item.title }}</h4>
               <div class="w-full bg-gray-200 rounded-full h-2.5 dark:bg-gray-700 mt-4">
                  <div class="bg-blue-600 h-2.5 rounded-full" style="width: 1%"></div>
               </div>
               <p class="text-sm font-medium text-slate-500 mt-2"><span class="font-medium text-blue-500">Rp 0,000</span> terkumpul dari Rp {{ Number(item.target_donation).toLocaleString() }}</p>

               <div class="flex items-center gap-2 mt-4">
                  <img class="w-7 rounded-full" :src="item.user.avatar" alt="" />
                  <p class="text-sm text-slate-500 font-medium">{{ item.user.name }}</p>
               </div>
               <button class="bg-blue-500 hover:bg-blue-700 text-white py-2 font-bold rounded-md mt-4">Donasi</button>
            </div>
         </div>
      </div>
   </section>
</template>
