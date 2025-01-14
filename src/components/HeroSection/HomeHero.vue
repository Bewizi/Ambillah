<script lang="ts" setup>
import { computed, onMounted, onUnmounted, ref } from 'vue'

interface Props {
  desktopImage: string
  mobileImage: string
  // bar?: number
}

const props = defineProps<Props>()

const isMobile = ref(false)
const isIntersecting = ref(false)
const lazyImageSrc = ref('')

const checkScreenSize = () => {
  isMobile.value = window.innerWidth <= 640
}

const imageSrc = computed(() => (isMobile.value ? props.desktopImage : props.mobileImage))

const observeElement = (element: Element | null) => {
  if (!element) return

  const observer = new IntersectionObserver(
    ([entries]) => {
      if (entries.isIntersecting) {
        isIntersecting.value = true
        observer.disconnect()
      }
    },
    { rootMargin: '50px' },
  )
  observer.observe(element)
}

onMounted(() => {
  checkScreenSize()
  window.addEventListener('resize', checkScreenSize)

  const lazyImageElement = document.querySelector('#lazyImage')
  observeElement(lazyImageElement)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkScreenSize)
})

const headerOneText = ['Innovation', 'Build', 'Deliver']
const currentIndex = ref(0)
let interval: number | undefined

const cycleText = () => {
  currentIndex.value = (currentIndex.value + 1) % headerOneText.length
}

onMounted(() => {
  interval = window.setInterval(cycleText, 5000)
})

onUnmounted(() => {
  clearInterval(interval)
})
</script>

<template>
  <div class="hero h-[100vh] bg-cover bg-center bg-[url('/images/img.png')]">
    <div class="container max-w-4xl mx-auto text-center sm:text-center md:text-start pt-32 mb-5">
      <div class="text-container overflow-hidden h-[60px] md:h-[100px] relative">
        <transition mode="out-in" name="slide-vertical">
          <h1 :key="currentIndex" class="text-5xl sm:text-6xl md:text-8xl font-bold font-Raleway">
            {{ headerOneText[currentIndex] }}
          </h1>
        </transition>
      </div>
      <p class="max-w-full sm:max-w-full md:max-w-sm font-Poppins font-light">
        Creating Digital Experiences that Inspire.  Creativity meets technical precision
      </p>
    </div>

    <div class="relative">
      <figure class="w-full">
        <img :src="imageSrc" alt="3D virtual assistance" />
      </figure>

      <div class="absolute -top-12 right-0 md:right-8 lg:right-28 md:-top-28 lg:-top-28">
        <img alt="" class="w-20 md:w-48 lg:w-48" src="/images/img_2.png" />
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

.slide-vertical-enter-active,
.slide-vertical-leave-active {
  transition:
    transform 0.5s ease-in-out,
    opacity 0.5s ease-in-out;
}

.slide-vertical-enter-from {
  transform: translateY(100%);
  opacity: 0;
}

.slide-vertical-leave-to {
  transform: translateY(-100%);
  opacity: 0;
}
</style>
