<script lang="ts" setup>
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuTrigger,
} from '@/components/ui/dropdown-menu'
import { Button } from '@/components/ui/button'
import { services } from '@/data/service'

defineProps<{
  service: Array<{
    title: string
    services: string[]
    color: string
    icon: string
  }>
  isExpanded?: boolean
}>()
</script>

<template>
  <section class="container max-w-4xl mx-auto flex flex-col items-center w-full gap-5 mt-10">
    <DropdownMenu v-for="service in services" :key="service.title">
      <DropdownMenuTrigger
        :style="{ backgroundColor: service.color }"
        as-child
        class="w-full flex items-center justify-between rounded-lg"
      >
        <Button class="w-full py-8 font-bold text-xl bg-transparent hover:bg-transparent">
          {{ service.title }}
          <i class="pi pi-sort-down-fill font-normal text-base"></i>
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent
        class="bg-transparent border-none text-white min-w-[20rem] sm:min-w-[38rem] md:min-w-[45rem]"
      >
        <div :style="{ backgroundColor: service.color }" class="rounded-lg">
          <DropdownMenuLabel class="text-2xl">{{ service.title }}</DropdownMenuLabel>
          <DropdownMenuItem :style="{ backgroundColor: service.color }">
            <ul
              class="list-none mt-6 space-y-2 p-0 m-0 w-full text-left text-white transition-opacity duration-500 ease-in-out opacity-100"
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
          </DropdownMenuItem>
        </div>
      </DropdownMenuContent>
    </DropdownMenu>
  </section>
</template>

<style scoped></style>
