<script lang="ts" setup>
import { Button } from '@/components/ui/button'
import { onMounted, onUnmounted, ref } from 'vue'

const isOpen = ref(false)
const isActive = ref('Home')
const isScrolled = ref(false)

const toggleNavbar = () => {
  isOpen.value = !isOpen.value
}

const updateActive = (route: string) => {
  isActive.value = route
}

const getActiveLink = (route: string) => {
  return isActive.value === route
    ? 'bg-black p-2 rounded-md drop-shadow-lg border-b-2 border-b-red-700 transition-all duration-700 ease-in-out'
    : ''
}

const handleIntersection = (entrires: IntersectionObserverEntry[]) => {
  isScrolled.value = !entrires[0].isIntersecting
}

onMounted(() => {
  const observer = new IntersectionObserver(handleIntersection, {
    root: null,
    threshold: 0.1,
  })

  const target = document.querySelector('#hero-section')
  if (target) observer.observe(target)

  onUnmounted(() => {
    if (target) observer.unobserve(target)
  })
})
</script>

<template>
  <header :class="[isScrolled ? 'bg-neutral-900 sticky z-50' : 'bg-neutral-900/50']">
    <div class="hidden md:block">
      <section class="max-w-4xl mx-auto flex items-center justify-between md:px-4 py-8">
        <div>
          <figure>
            <img alt="" src="/images/logo.png" />
          </figure>
        </div>

        <nav class="flex items-center justify-center gap-10 font-Poppins font-light">
          <router-link :class="getActiveLink('Home')" to="/" @click="updateActive('Home')"
            >Home
          </router-link>
          <router-link to="/">Our services</router-link>
          <router-link
            :class="getActiveLink('Careers')"
            to="/about"
            @click="updateActive('Careers')"
            >Careers</router-link
          >
          <router-link
            :class="getActiveLink('Portfolio')"
            to="/portfolio"
            @click="updateActive('Portfolio')"
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
            <img alt="" src="/images/logo.png" />
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
          :class="{ 'h-[40vh] opacity-100': isOpen, 'h-0 opacity-0 overflow-hidden': !isOpen }"
          class="flex flex-col items-start pl-5 justify-start gap-6 font-Poppins font-light bg-[#070D04]/50 absolute inset-x-0 top-16 transition-all duration-300 z-10"
        >
          <router-link :class="getActiveLink('Home')" to="/" @click="updateActive('Home')"
            >Home</router-link
          >
          <router-link to="">Our services</router-link>
          <router-link
            :class="getActiveLink('Careers')"
            to="/about"
            @click="updateActive('Careers')"
            >Careers</router-link
          >
          <router-link
            :class="getActiveLink('Portfolio')"
            to="/portfolio"
            @click="updateActive('Portfolio')"
            >Our portfolio</router-link
          >
        </nav>
      </section>
    </div>
  </header>
</template>

<style scoped>
header {
  transition: background-color 0.3s ease;
}
</style>
