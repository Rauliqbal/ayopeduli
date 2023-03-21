<script setup>
useHead({
   title: "Home - Nuxt 3 with Tailwind",
});
</script>
<template>
   <main class="flex items-center justify-center flex-col">
      <div class="pt-40 flex flex-col items-center">
         <a href="#" class="text-sm items-center inline-flex py-1 px-2 border border-gray-400 hover:border-green-500 bg-white hover:bg-gray-100 rounded-full">
            <img class="w-6 rounded-full mr-1" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" alt="" />
            Github Repository</a
         >
         <h1 class="text-4xl md:text-5xl font-semibold text-gray-600 text-center mt-4">Nuxt 3 with Tailwind CSS</h1>
         <p class="text-lg text-gray-400 mt-8 text-center">This template will help you start developing<br />with Nuxt 3 and Tailwind CSS</p>
         <div class="absolute inset-x-0 mt-[-240px] -z-10 transform-gpu overflow-hidden blur-3xl">
            <div class="relative bg-green-300 blur-2xl h-40 max-w-[600px]"></div>
         </div>
         <div class="absolute right-0 -z-10 transform-gpu overflow-hidden blur-3xl">
            <div class="relative bg-green-300 blur-2xl h-40 w-96"></div>
         </div>
      </div>
      <div class="flex gap-8 mt-10">
         <a href="https://nuxt.com/docs" class="bg-white py-3 px-6 border border-gray-400 flex items-center gap-4 font-medium text-lg rounded-lg hover:border-green-500 hover:bg-gray-100 transition-all">
            <img class="w-10" src="https://nuxt.com/assets/design-kit/logo/icon-green.svg" alt="" />
            Nuxt Docs
         </a>
         <a href="https://tailwindcss.com/" class="bg-white py-3 px-6 border border-gray-400 flex items-center gap-4 font-medium text-lg rounded-lg hover:border-green-500 hover:bg-gray-100 transition-all">
            <img class="w-10" src="https://tailwindcss.com/_next/static/media/tailwindcss-mark.79614a5f61617ba49a0891494521226b.svg" alt="" />
            Tailwind Docs
         </a>
      </div>
   </main>
</template>
