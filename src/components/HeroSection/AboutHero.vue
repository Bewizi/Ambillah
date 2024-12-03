<script lang="ts" setup>
import { Button } from '@/components/ui/button'
</script>

<template>
  <section class="hero h-[100vh] bg-cover bg-center bg-[url('/images/img_13.png')]">
    <div class="max-w-4xl mx-auto">
      <div class="flex flex-col items-center justify-center text-center h-[100vh]">
        <h1 class="text-4xl md:text-6xl lg:text-7xl font-bold">
          Join our team of <br />
          creatives and innovators
        </h1>
        <p class="font-Poppins font-light">
          We are driven by a passion for technology and innovation
        </p>
        <div class="flex items-center justify-center mt-5">
          <Button class="bg-[#C90202] hover:bg-[#C90202]/65 font-Poppins font-light px-10 py-5"
            >Join our team</Button
          >
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  display: grid;
  grid-template-columns: 1fr;
  grid-row: auto;
}
</style>
