<template>
  <main class="">
    <AboutHero />

    <!--  About Company   -->
    <section
      class="container max-w-4xl mx-auto flex flex-col items-center gap-10 lg:mt-32 sm:flex-row"
    >
      <div
        class="flex flex-col items-center text-center md:items-start md:text-start lg:items-start"
      >
        <h1 class="text-5xl font-bold mb-5">About us</h1>
        <p class="font-Poppins font-light mb-4 leading-loose md:leading-relaxed">
          At Ambillah, we are driven by a passion for technology and innovation. Our mission is to
          build cutting-edge tech products that transform businesses and enhance user experiences.
          We're looking for talented, creative, and driven individuals to join our dynamic team and
          help us achieve our goals.
        </p>
      </div>
      <figure class="">
        <img alt="" src="/images/img_14.png" width="1800px" />
      </figure>
    </section>
    <!--  About Company   -->

    <CompanysGoals />

    <!--  Services  -->
    <ServiceSection />
    <!--  Services  -->
  </main>
</template>

<style></style>
<script lang="ts" setup>
import AboutHero from '@/components/HeroSection/AboutHero.vue'
import CompanysGoals from '@/views/About/component/CompanysGoals.vue'
import ServiceSection from '@/components/services/ServiceSection.vue'
</script>
