<script lang="ts" setup>
import { services } from '@/data/service'
import { ref } from 'vue'
import { Button } from '@/components/ui/button'
import Dropdown from '@/components/services/Dropdown/Dropdown.vue'

const expandedCard = ref<string | null>(null)

const handleClick = (title: string) => {
  expandedCard.value = expandedCard.value === title ? null : title
}

const isHovered = ref(false)
const isSelected = ref(false)
const isHover = ref(false)
const isSelect = ref(false)

const serviceData = ref([
  'Brand Strategy & Positioning',
  'Visual Identity',
  'Brand Architecture',
  'Brand Guidelines',
  'Branding',
  'Design System & Style Guides',
  'Product UI/UX Design',
  'Website and Graphics Design',
])

const devList = ref([
  'Web Development',
  'Mobile Applications',
  'Progressive Web Apps (PWA)',
  'Accessibility Optimization',
  'SEO Optimization',
  'Component-Based Development',
])

const backendList = ref([
  'Data Visualization',
  'Data Modeling',
  'Descriptive and Exploratory Analysis',
  'Database Management',
  'ETL',
  'API Development',
  'Data Analytics Expression',
  'Business Intelligence',
])

const dataList = ref([
  'Data Visualization',
  'Data Modeling',
  'Descriptive/Exploratory Analysis',
  'Database Management',
  'ETL',
  'Data Analytics Exploration',
  'Business Inteligence',
])
</script>

<template>
  <section class="max-w-7xl mx-auto py-16 px-5 lg:px-8 mt-32 hidden lg:block">
    <h2 class="text-4xl font-bold text-center mb-12 text-white">Our Services</h2>
    <!--    <div class="flex flex-col md:flex-row gap-8 max-w-7xl mx-auto">-->
    <!--      <ServiceCard-->
    <!--        v-for="service in services"-->
    <!--        :key="service.title"-->
    <!--        :is-expanded="expandedCard === service.title"-->
    <!--        :service="service"-->
    <!--        @click="handleClick(service.title)"-->
    <!--      />-->
    <!--    </div>-->
    <!--    <div class="flex items-center justify-center mt-10">-->
    <!--      <Button class="bg-[#C90202] hover:bg-[#C90202]/65 font-Poppins font-light px-10 py-6"-->
    <!--        >Book us now</Button-->
    <!--      >-->
    <!--    </div>-->

    <section class="flex gap-5 items-center justify-center">
      <div
        :class="[
          'bg-[#C90202] mt-10 flex flex-col p-8 rounded-md  transition-all ease-in-out duration-500 relative',
          isHovered ? 'w-max font-bold text-2xl h-screen' : 'w-min h-[50vh]',
        ]"
        @mouseleave="isHovered = false"
        @mouseover="isHovered = true"
      >
        <h1 class="text-3xl">Design</h1>
        <!--      <p>hello</p>-->
        <ul :class="[isHovered ? 'block p-5 z-100' : 'hidden']">
          <li v-for="(items, index) in serviceData" :key="index" class="list-disc leading-relaxed">
            {{ items }}
          </li>
        </ul>
        <figure
          :class="['absolute  right-0', isHovered ? 'w-[20rem] bottom-0' : 'w-[10rem] bottom-8']"
        >
          <img alt="" src="/images/img_5.png" />
        </figure>
      </div>

      <!--   Development Services   -->
      <div
        :class="[
          'bg-[#3B82F6] mt-10 flex flex-col p-8 rounded-md  transition-all ease-in-out duration-500 relative',
          isSelected ? 'w-max font-bold text-2xl h-screen' : 'w-min h-[50vh]',
        ]"
        @mouseleave="isSelected = false"
        @mouseover="isSelected = true"
      >
        <h1 class="text-3xl">Development</h1>
        <!--      <p>hello</p>-->
        <ul :class="[isSelected ? 'block p-5 z-100' : 'hidden']">
          <li v-for="(items, index) in devList" :key="index" class="list-disc leading-relaxed">
            {{ items }}
          </li>
        </ul>
        <figure
          :class="['absolute', isSelected ? 'w-[20rem]  right-0 bottom-0' : 'w-[10rem] bottom-0']"
        >
          <img alt="" src="/images/img_6.png" />
        </figure>
      </div>

      <!--   Backend Services   -->

      <div
        :class="[
          'bg-[#F97316] mt-10 flex flex-col p-8 rounded-md  transition-all ease-in-out duration-500 relative',
          isHover ? 'w-max font-bold text-2xl h-screen' : 'w-min h-[50vh]',
        ]"
        @mouseleave="isHover = false"
        @mouseover="isHover = true"
      >
        <h1 class="text-3xl">Backend</h1>
        <!--      <p>hello</p>-->
        <ul :class="[isHover ? 'block p-5 z-100' : 'hidden']">
          <li v-for="(items, index) in backendList" :key="index" class="list-disc leading-relaxed">
            {{ items }}
          </li>
        </ul>
        <figure :class="['absolute ', isHover ? 'w-[20rem]  right-0 bottom-0' : 'w-full bottom-0']">
          <img alt="" src="/images/img_7.png" />
        </figure>
      </div>

      <!--    Data service  -->
      <div
        :class="[
          'bg-[#7C3AED] mt-10 flex flex-col p-8 rounded-md  transition-all ease-in-out duration-500 relative',
          isSelect ? 'w-max font-bold text-2xl h-screen' : 'w-min h-[50vh] overflow-x-hidden',
        ]"
        @mouseleave="isSelect = false"
        @mouseover="isSelect = true"
      >
        <h1 class="text-3xl">Data</h1>
        <!--      <p>hello</p>-->
        <ul :class="[isSelect ? 'block p-5 z-100' : 'hidden']">
          <li v-for="(items, index) in dataList" :key="index" class="list-disc leading-relaxed">
            {{ items }}
          </li>
        </ul>
        <figure
          :class="['absolute ', isSelect ? 'w-[20rem]  right-0 bottom-0' : 'w-full bottom-0']"
        >
          <img alt="" src="/images/img_8.png" />
        </figure>
      </div>
    </section>
    <div class="flex items-center justify-center mt-10">
      <Button class="bg-[#C90202] hover:bg-[#C90202]/65 font-Poppins font-light px-10 py-6"
        >Book us now</Button
      >
    </div>
  </section>

  <div class="block lg:hidden">
    <Dropdown :service="services" class="w-full" />
    <div class="flex items-center justify-center mt-5">
      <Button class="bg-[#C90202] hover:bg-[#C90202]/65 font-Poppins font-light px-10 py-8"
        >Book us now</Button
      >
    </div>
  </div>
</template>

<style scoped></style>
