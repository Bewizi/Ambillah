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
  <section class="max-w-4xl mx-auto mt-20 md:mt-48 px-5 sm:px-8 lg:px-0">
    <div class="grid place-items-center">
      <h1
        class="font-semibold text-4xl leading-normal text-center font-Raleway mb-8 md:text-6xl lg:leading-tight md:mb-10 lg:mb-14"
      >
        Why Work With Us?
      </h1>

      <div
        class="grid grid-cols-1 sm:grid-cols-2 gap-y-5 lg:grid-cols-3 md:gap-x-12 md:gap-y-4 lg:gap-y-8"
      >
        <Card
          v-for="(item, index) in array"
          :key="index"
          class="border-2 border-[#1E1E1E] bg-[#0A0A0A] text-white text-center py-8 md:min-h-[40vh] lg:min-h-[50vh] grid place-content-center px-5"
        >
          <h2
            class="font-medium text-4xl font-Raleway lg:text-4xl mb-5 leading-relaxed lg:leading-tight"
          >
            {{ item.mainHeader }}
          </h2>
          <p class="font-light font-Poppins leading-loose">{{ item.mainText }}</p>
        </Card>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
