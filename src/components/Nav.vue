<script lang="ts" setup>
import { Button } from '@/components/ui/button'
import HomeView from '@/views/Home/HomeView.vue'
import AboutView from '@/views/About/AboutView.vue'
import PortfolioView from '@/views/Portfolio/PortfolioView.vue'
import { ref } from 'vue'

const isOpen = ref(false)
const isActive = ref('Home')
const show = ref<any>(HomeView)

const toggleNavbar = () => {
  isOpen.value = !isOpen.value
}

const updateActive = (route: string, component: any) => {
  isActive.value = route
  show.value = component
}

const getActiveLink = (route: string) => {
  return isActive.value === route
    ? 'bg-black p-2 rounded-md drop-shadow-lg border-b-2 border-b-red-700 transition-all duration-700 ease-in-out'
    : ''
}
</script>

<template>
  <header class="bg-neutral-900/50">
    <div class="hidden md:block">
      <section class="max-w-4xl mx-auto flex items-center justify-between md:px-4 py-8">
        <div>
          <figure>
            <img alt="" src="/images/img_10.png" />
          </figure>
        </div>

        <nav class="flex items-center justify-center gap-10 font-Poppins font-light">
          <router-link
            :class="getActiveLink('Home')"
            to="/"
            @click.prevent="updateActive('Home', HomeView)"
            >Home
          </router-link>
          <router-link to="/">Our services</router-link>
          <router-link
            :class="getActiveLink('Careers')"
            to="/about"
            @click.prevent="updateActive('Careers', AboutView)"
            >Careers</router-link
          >
          <router-link
            :class="getActiveLink('portfolio')"
            to="/portfolio"
            @click.prevent="updateActive('portfolio', PortfolioView)"
            >Our portfolio</router-link
          >
        </nav>

        <div>
          <Button class="bg-[#C90202] hover:bg-[#C90202]/65 text-white py-5">Book us</Button>
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

  <main>
    <Transition name="fade">
      <component :is="show" key="isActive" />
    </Transition>
  </main>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
