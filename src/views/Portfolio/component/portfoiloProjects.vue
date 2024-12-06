<script lang="ts" setup>
import VLazyImage from 'v-lazy-image'
import { Card } from '@/components/ui/card'

const projectImage = [
  {
    image: '/images/img_16.png',
  },
  {
    image: '/images/img_17.png',
  },
  {
    image: '/images/img_18.png',
  },
  {
    image: '/images/img_19.png',
  },
  {
    image: '/images/img_20.png',
  },
]
</script>

<template>
  <main class="max-w-4xl mx-auto px-5 lg:px-0">
    <div class="flex flex-col gap-8">
      <Card v-for="(items, index) in projectImage" :key="index" class="bg-transparent border-none">
        <figure>
          <v-lazy-image :src="items.image" alt="" class="rounded-lg" loading="lazy" />
        </figure>
      </Card>
    </div>
  </main>
</template>

<style scoped></style>
