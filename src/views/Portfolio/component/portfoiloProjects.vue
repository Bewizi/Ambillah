<script lang="ts" setup>
import { Card } from '@/components/ui/card'

const projectImage = [
  {
    image: '/images/Brand_Indentity.png',
    text: 'Brand Identity Design',
  },
  {
    image: '/images/AI-Generated-Image.png',
    text: 'Telegram AI \n' + 'Image Generator',
  },
  {
    image: '/images/Brand_Design.png',
    text: 'Brand Design',
  },
]
</script>

<template>
  <main class="max-w-4xl mx-auto px-5 lg:px-0">
    <div class="flex flex-col gap-8">
      <Card v-for="(item, index) in projectImage" :key="index" class="bg-transparent border-none">
        <figure class="relative">
          <img :src="item.image" alt="" class="rounded-lg object-cover" />
          <div
            class="absolute bottom-0 w-full h-28 bg-black/50 text-white flex items-center justify-start pl-5 opacity-0 transition-opacity duration-500 hover:opacity-100"
          >
            <h1 class="font-bold text-4xl font-Poppins">{{ item.text }}</h1>
          </div>
        </figure>
      </Card>
    </div>
  </main>
</template>

<style scoped>
figure:hover .absolute {
  opacity: 1;
}
</style>
