<template>
  <footer class="bg-[#141414] mt-32 md:px-5 lg:px-0">
    <header class="max-w-7xl mx-auto py-10">
      <section class="flex flex-col items-center justify-center">
        <div class="mb-5">
          <figure>
            <img alt="" src="/images/logo.png" />
          </figure>
        </div>
        <nav class="font-Poppins text-lg space-x-5 font-normal">
          <router-link to="/about">About</router-link>
          <router-link to="">Careers</router-link>
          <router-link to="/portfolio">Portfoilo</router-link>
        </nav>
      </section>
      <hr class="mt-10" />
      <div class="mx-auto flex flex-col md:flex-row items-center justify-between mt-8">
        <p class="mb-5 lg:mb-0">&copy; 2024 Ambillah. All rights reserved</p>
        <div class="space-x-5">
          <i class="pi pi-instagram bg-gray-900 p-2 rounded-full"></i>
          <i class="pi pi-twitter bg-gray-900 p-2 rounded-full"></i>
          <i class="pi pi-youtube bg-gray-900 p-2 rounded-full"></i>
        </div>
      </div>
    </header>
  </footer>
</template>
