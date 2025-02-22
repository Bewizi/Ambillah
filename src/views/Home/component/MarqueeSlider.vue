<script lang="ts" setup>
import { Button } from '@/components/ui/button'

const helloArray = ['Evolve', 'Evolve', 'Evolve', 'Evolve', 'Evolve', 'Evolve']
</script>

<template>
  <div class="container max-w-7xl mx-auto mt-32 px-5 md:px-8 h-0">
    <div class="h-[100px] overflow-hidden">
      <div class="flex slide-content">
        <span
          v-for="(word, index) in helloArray.concat(helloArray)"
          :key="index"
          class="mr-12 text-6xl font-Raleway"
        >
          {{ word }}
        </span>
      </div>
    </div>
  </div>

  <section class="max-w-4xl mx-auto mt-32 md:px-8 lg:px-8">
    <div class="linear">
      <div class="flex flex-col items-center justify-center font-Poppins">
        <h2 class="text-4xl font-bold mb-10 text-center leading-relaxed">
          Reimagine Your Brand's Future
        </h2>
        <Button class="bg-[#C90202] hover:bg-[#C90202]/65 py-6">
          <a href="https://forms.gle/RRYYKr4jBF7uyz3Y8" rel="noopener noreferrer" target="_blank">
            Book a free consultation.
          </a>
        </Button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.linear {
  position: relative;
  border: none;
  padding: 2px;
  border-radius: 8px;

  background: linear-gradient(90deg, #9747ff, #f1ae00);
}

.linear > * {
  background: #141414;
  border-radius: 6px;
  padding: 5rem 0;
}

.slide-content {
  animation: slide 10s infinite linear;
  white-space: nowrap;
}

@keyframes slide {
  0% {
    transform: translateX(0);
  }

  100% {
    transform: translateX(-100%);
  }
}
</style>
