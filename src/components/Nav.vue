<script lang="ts" setup>
import { Button } from '@/components/ui/button'
</script>

<template>
  <header class="bg-[#070D041A]">
    <section class="max-w-4xl mx-auto flex items-center justify-between py-4">
      <div>
        <figure>
          <img alt="" src="/images/img_10.png" />
        </figure>
      </div>
      <nav class="space-x-8 font-Poppins font-light">
        <router-link to="/">Home</router-link>
        <router-link to="/about">Our services</router-link>
        <router-link to="/about">Careers</router-link>
        <router-link to="/about">Our portfolio</router-link>
      </nav>
      <div>
        <Button class="bg-[#C90202] hover:bg-[#C90202]/65 text-white">Book us</Button>
      </div>
    </section>
  </header>
</template>

<style scoped></style>
