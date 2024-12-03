<script lang="ts" setup>
import { Button } from '@/components/ui/button'
import { ref } from 'vue'

const isOpen = ref(false)

const toggleNavbar = () => {
  isOpen.value = !isOpen.value
}
</script>

<template>
  <header class="bg-[#070D041A]">
    <div class="hidden md:block">
      <section class="max-w-4xl mx-auto flex items-center justify-between md:px-4 py-4">
        <div>
          <figure>
            <router-link to="/">
              <img alt="Logo" src="/images/img_10.png" />
            </router-link>
          </figure>
        </div>

        <nav class="flex items-center justify-center gap-10 font-Poppins font-light">
          <router-link to="/">Home</router-link>
          <router-link to="/">Our services</router-link>
          <router-link to="/about">Careers</router-link>
          <router-link to="/portfolio">Our portfolio</router-link>
        </nav>

        <div>
          <Button class="bg-[#C90202] hover:bg-[#C90202]/65 text-white">Book us</Button>
        </div>
      </section>
    </div>

    <div class="block md:hidden">
      <section class="flex items-center justify-between px-4 py-4">
        <div>
          <figure>
            <img alt="" src="/images/img_10.png" />
          </figure>
        </div>

        <section class="flex items-center gap-5">
          <div>
            <Button class="bg-[#C90202] hover:bg-[#C90202]/65 text-white">Book us</Button>
          </div>
          <!--  icon -->
          <div class="flex items-center">
            <i v-if="!isOpen" class="pi pi-bars hidden" @click="toggleNavbar"></i>
            <i v-else class="pi pi-times" @click="toggleNavbar"></i>
          </div>
          <!--  icon -->
        </section>

        <nav
          :class="{ 'h-48 opacity-100': isOpen, 'h-0 opacity-0 overflow-hidden': !isOpen }"
          class="flex flex-col items-center justify-center gap-6 font-Poppins font-light bg-[#070D04]/50 absolute inset-x-0 top-16 transition-all duration-300 z-10"
        >
          <router-link to="/">Home</router-link>
          <router-link to="/">Our services</router-link>
          <router-link to="/about">Careers</router-link>
          <router-link to="/portfolio">Our portfolio</router-link>
        </nav>
      </section>
    </div>
  </header>
</template>

<style scoped></style>
