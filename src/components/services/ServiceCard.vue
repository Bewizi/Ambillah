<script lang="ts" setup>
defineProps<{
  service: {
    title: string
    services: string[]
    color: string
    icon: string
  }
  isExpanded: boolean
}>()
</script>

<template>
  <div
    :style="{
      backgroundColor: service.color,
      width: isExpanded ? '100%' : 'calc(100% / 2)',
    }"
    class="max-w-2xl mx-auto p-8 rounded-2xl text-white transition-all duration-500 ease-in-out cursor-pointer min-h-[50vh]"
  >
    <div class="flex flex-col relative min-h-[50vh]">
      <!-- Title -->
      <h3
        :class="isExpanded ? 'text-start text-4xl' : ' text-2xl'"
        class="font-bold transition-all duration-500 ease-in-out"
      >
        {{ service.title }}
      </h3>

      <!-- Services List -->
      <ul
        v-if="isExpanded"
        class="list-none mt-6 space-y-2 p-0 m-0 w-full text-left transition-opacity duration-500 ease-in-out opacity-100"
      >
        <li
          v-for="item in service.services"
          :key="item"
          class="flex items-center mb-2 font-Poppins"
        >
          <span class="mr-2 text-lg font-bold">•</span>
          <span>{{ item }}</span>
        </li>
      </ul>

      <!-- Image -->
      <figure
        :class="
          isExpanded
            ? 'absolute bottom-0 right-0 '
            : 'absolute bottom-0 mx-auto flex items-center justify-center'
        "
        class="transition-all duration-500 ease-in-out"
      >
        <img
          :alt="service.title"
          :class="isExpanded ? 'w-48 h-48' : 'w-full'"
          :src="service.icon"
          class="object-cover transition-all duration-500 ease-in-out"
        />
      </figure>
    </div>
  </div>
</template>

<style scoped>
/* Add additional scoped styles if necessary */
</style>
