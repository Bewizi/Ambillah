<script lang="ts" setup>
import { Vue3Marquee } from 'vue3-marquee'
import { Button } from '@/components/ui/button'

const helloArray = ['Evolve', 'Evolve', 'Evolve', 'Evolve', 'Evolve', 'Evolve']
</script>

<template>
  <div class="container max-w-7xl mx-auto mt-32 px-5 md:px-8 h-0">
    <Vue3Marquee>
      <span v-for="(word, index) in helloArray" :key="index" class="mr-12 text-6xl">
        {{ word }}
      </span>
    </Vue3Marquee>
  </div>

  <section class="max-w-4xl mx-auto mt-32 md:px-8 lg:px-8">
    <div class="linear">
      <div class="flex flex-col items-center justify-center font-Poppins">
        <h2 class="text-4xl font-bold mb-10 text-center">Reimagine Your Brand's Future</h2>
        <Button class="bg-[#C90202] hover:bg-[#C90202]/65 py-6">Book a free consultation</Button>
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
</style>
