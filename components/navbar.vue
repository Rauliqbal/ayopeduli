<script setup>
function showHide() {
   document.getElementById("hamburger").checked = false;
}

const links = [
   {
      title: "Beranda",
      url: "/",
   },
   {
      title: "Donasi",
      url: "/",
   },
   {
      title: "Kategori",
      url: "/",
   },
   {
      title: "Santunan",
      url: "/",
   },
];
</script>

<template>
   <nav class="fixed inset-x-0 top-0 z-30 py-4 md:py-6 bg-white shadow-md">
      <div class="container">
         <div class="flex items-center justify-between">
            <div class="relative">
               <NuxtLink to="/" class="text-blue-500 font-bold text-2xl flex items-center gap-2"
                  ><svg id="logo-86" width="32" height="32" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
                     <path
                        class="ccustom"
                        fill-rule="evenodd"
                        clip-rule="evenodd"
                        d="M25.5557 11.6853C23.9112 10.5865 21.9778 10 20 10V0C23.9556 0 27.8224 1.17298 31.1114 3.37061C34.4004 5.56823 36.9638 8.69181 38.4776 12.3463C39.9913 16.0008 40.3874 20.0222 39.6157 23.9018C38.844 27.7814 36.9392 31.3451 34.1421 34.1421C31.3451 36.9392 27.7814 38.844 23.9018 39.6157C20.0222 40.3874 16.0008 39.9913 12.3463 38.4776C8.69181 36.9638 5.56823 34.4004 3.37061 31.1114C1.17298 27.8224 0 23.9556 0 20H10C10 21.9778 10.5865 23.9112 11.6853 25.5557C12.7841 27.2002 14.3459 28.4819 16.1732 29.2388C18.0004 29.9957 20.0111 30.1937 21.9509 29.8078C23.8907 29.422 25.6725 28.4696 27.0711 27.0711C28.4696 25.6725 29.422 23.8907 29.8078 21.9509C30.1937 20.0111 29.9957 18.0004 29.2388 16.1732C28.4819 14.3459 27.2002 12.7841 25.5557 11.6853Z"
                        fill="#007DFC"
                     ></path>
                     <path
                        class="ccustom"
                        fill-rule="evenodd"
                        clip-rule="evenodd"
                        d="M10 5.16562e-07C10 1.31322 9.74135 2.61358 9.2388 3.82683C8.73625 5.04009 7.99966 6.14248 7.07107 7.07107C6.14249 7.99966 5.0401 8.73625 3.82684 9.2388C2.61358 9.74134 1.31322 10 5.4439e-06 10L5.00679e-06 20C2.62644 20 5.22716 19.4827 7.65368 18.4776C10.0802 17.4725 12.285 15.9993 14.1421 14.1421C15.9993 12.285 17.4725 10.0802 18.4776 7.65367C19.4827 5.22715 20 2.62643 20 -3.81469e-06L10 5.16562e-07Z"
                        fill="#007DFC"
                     ></path></svg
                  >AyoPeduli</NuxtLink
               >
            </div>
            <div class="flex items-center">
               <input type="checkbox" class="peer hidden" name="hamburger" id="hamburger" />
               <label for="hamburger" class="peer-checked:hamburger z-50 p-4 block cursor-pointer md:hidden">
                  <span class="transition duration-200 inline-block w-7 h-1 bg-black rounded-xl after:rounded-xl before:rounded-xl"></span>
               </label>
               <div @click="showHide" class="z-30 absolute inset-0 h-screen bg-gray-900/30 backdrop-blur-sm opacity-0 hidden peer-checked:opacity-100 peer-checked:block transition-all duration-300 md:peer-checked:hidden"></div>
               <div class="peer-checked:translate-x-0 w-72 fixed top-0 right-0 bottom-0 translate-x-full transition duration-300 md:w-auto md:static md:translate-x-0 z-40 ease-out">
                  <div class="flex flex-col md:items-center md:flex-row h-full">
                     <ul class="bg-white flex px-7 pt-28 md:pb-0 pb-[38rem] space-y-8 md:px-0 md:space-y-0 flex-col md:flex-row md:space-x-12 md:pt-0">
                        <li v-for="link in links" :key="link">
                           <NuxtLink @click="showHide" class="capitalize font-semibold tracking-wide hover:text-blue-700 transition ease-out duration-200 text-gray-500" :to="link.url">{{ link.title }}</NuxtLink>
                        </li>
                     </ul>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </nav>
</template>

<style>
#hamburger ~ label span::after,
#hamburger ~ label span::before {
   background: #000;
   transition-delay: 0.2s, 0s;
   transition-duration: 0.1s;
   transition-property: margin, transform;
   content: "";
   position: absolute;
   width: 28px;
   height: 4px;
}

#hamburger ~ label span::after {
   margin-top: 10px;
}

#hamburger ~ label span::before {
   margin-top: -10px;
}

#hamburger:checked ~ label span {
   background-color: transparent;
}

#hamburger:checked ~ label span:before,
#hamburger:checked ~ label span:after {
   transition-delay: 0s, 0.2s;
   margin-top: 0;
}

#hamburger:checked ~ label span:before {
   transform: rotate(45deg);
}

#hamburger:checked ~ label span:after {
   transform: rotate(-45deg);
}
</style>
