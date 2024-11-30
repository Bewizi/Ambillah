<script lang="ts" setup>
import ServiceCard from '@/components/services/ServiceCard.vue'
import { services } from '@/data/service'
import { ref } from 'vue'
import { Button } from '@/components/ui/button'

const expandedCard = ref<string | null>(null)

const handleClick = (title: string) => {
  expandedCard.value = expandedCard.value === title ? null : title
}
</script>

<template>
  <section class="max-w-7xl mx-auto py-16 px-5 lg:px-8 mt-32">
    <h2 class="text-4xl font-bold text-center mb-12 text-white">Our Services</h2>
    <div class="flex flex-col md:flex-row gap-8 max-w-7xl mx-auto">
      <ServiceCard
        v-for="service in services"
        :key="service.title"
        :is-expanded="expandedCard === service.title"
        :service="service"
        @click="handleClick(service.title)"
      />
    </div>
    <div class="flex items-center justify-center mt-10">
      <Button class="bg-[#C90202] hover:bg-[#C90202]/65 font-Poppins font-light px-10 py-5"
        >Book us now</Button
      >
    </div>
  </section>
</template>

<style scoped></style>
