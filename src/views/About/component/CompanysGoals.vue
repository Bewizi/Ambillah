<script lang="ts" setup>
import { Card } from '@/components/ui/card'

const array = [
  {
    mainHeader: 'Innovative Environment',
    mainText:
      'Collaborate with a team of forward-thinkers and industry experts who are passionate about creating impactful solutions',
  },
  {
    mainHeader: 'Growth Opportunities',
    mainText:
      'We invest in your professional development with training programs, mentorship, and opportunities to advance your career.',
  },
  {
    mainHeader: 'Exciting Projects',
    mainText:
      "Work on diverse projects that challenge your skills and push the boundaries of what's possible in tech.",
  },
  {
    mainHeader: 'Inclusive Culture',
    mainText:
      'Join a supportive and inclusive work environment where your ideas are valued, and diversity is celebrated.',
  },
  {
    mainHeader: 'Flexible Work Arrangements',
    mainText:
      'Enjoy the flexibility of remote work options, flexible hours, and a healthy work-life balance.',
  },
]
</script>

<template>
  <section class="max-w-4xl mx-auto mt-32 px-5 sm:px-8 lg:px-0">
    <div class="grid place-items-center">
      <h1 class="font-bold lg:text-6xl mb-10">Why Work With Us?</h1>

      <div class="grid grid-cols-2 sm:grid-cols-2 lg:grid-cols-3 gap-5">
        <Card
          v-for="(item, index) in array"
          :key="index"
          class="border-2 border-[#1E1E1E] bg-[#0A0A0A] text-white text-center min-h-[50vh] grid place-content-center px-5"
        >
          <h2 class="font-bold text-2xl md:text-4xl lg:text-4xl mb-5">{{ item.mainHeader }}</h2>
          <p class="font-light font-Poppins">{{ item.mainText }}</p>
        </Card>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
