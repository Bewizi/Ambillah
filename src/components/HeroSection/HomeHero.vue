<script lang="ts" setup>
import { computed, onMounted, onUnmounted, ref } from 'vue'

interface Props {
  desktopImage: string
  mobileImage: string
  // bar?: number
}

const props = defineProps<Props>()

const isMobile = ref(false)

const checkScreenSize = () => {
  isMobile.value = window.innerWidth <= 640
}

onMounted(() => {
  checkScreenSize()
  window.addEventListener('resize', checkScreenSize)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkScreenSize)
})

const imageSrc = computed(() => (isMobile.value ? props.desktopImage : props.mobileImage))
</script>

<template>
  <div class="hero h-[100vh] bg-cover bg-center bg-[url('/images/img.png')]">
    <div class="container max-w-4xl mx-auto text-center sm:text-center md:text-start pt-32 mb-5">
      <h1 class="text-4xl sm:text-6xl md:text-8xl mb-2">Innovation</h1>
      <p class="max-w-full sm:max-w-full md:max-w-sm font-Poppins font-light">
        Creating Digital Experiences that Inspire.  Creativity meets technical precision
      </p>
    </div>

    <div class="relative">
      <figure class="w-full">
        <img :src="imageSrc" alt="3D virtual assistance" />
      </figure>

      <div class="absolute -top-12 right-0 md:-top-28 lg:-top-48">
        <img alt="" class="w-20 md:w-48 lg:w-full" src="/images/img_2.png" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero {
  display: grid;
  grid-template-columns: 1fr;
  grid-row: auto;
}
</style>
