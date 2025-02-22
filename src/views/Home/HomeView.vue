<script lang="ts" setup>
import HomeHero from '@/components/HeroSection/HomeHero.vue'
import { Button } from '@/components/ui/button'
import ServiceSection from '@/components/services/ServiceSection.vue'
import MarqueeSlider from '@/views/Home/component/MarqueeSlider.vue'
import { onMounted } from 'vue'
import { Vue3Marquee } from 'vue3-marquee'

const lazyLoadImages = () => {
  const images = document.querySelectorAll('[data-src]')

  const observer = new IntersectionObserver(
    (entries, observerInstance) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const img = entry.target as HTMLImageElement
          img.src = img.dataset.src || ''
          img.removeAttribute('data-src')
          observerInstance.unobserve(img)
        }
      })
    },
    {
      rootMargin: '50px',
      threshold: 0.5,
    },
  )
  images.forEach((img) => observer.observe(img))
}

onMounted(() => {
  lazyLoadImages()
})
</script>

<template>
  <main class="min-h-screen">
    <HomeHero desktopImage="/images/img_12.png" mobileImage="/images/img_1.png" />

    <!--  Company Brand  -->
    <section
      class="container max-w-4xl mx-auto flex flex-col items-center mt-20 gap-10 md:mt-32 lg:mt-40 sm:flex-row py-24"
    >
      <div class="flex flex-col items-center text-center lg:text-start lg:items-start">
        <h1 class="text-4xl font-bold mb-5 font-Raleway lg:w-[30rem]">Kick-start your Branding!</h1>
        <p class="font-Poppins font-light mb-4 leading-loose md:leading-relaxed">
          Our agency specializes in developing comprehensive solutions to your backend and front-end
          design systems which grants your users and customers seamless access to your proucts
          and/or services, helping you maximise profit as you convert sales like never before. 
        </p>
        <Button
          class="bg-[#C90202] hover:bg-[#C90202]/65 font-Poppins font-light py-7 w-full lg:py-8 lg:w-fit text-lg"
        >
          <a href="https://forms.gle/RRYYKr4jBF7uyz3Y8" rel="noopener noreferrer" target="_blank">
            Book a free consultation.
          </a>
        </Button>
      </div>
      <figure class="hidden lg:block">
        <img
          alt=""
          class="lazy-img"
          data-src="/images/img_3.png"
          src="/images/img_3.png"
          width="1800px"
        />
      </figure>
    </section>
    <!--  Company Brand  -->

    <!--  Projects  -->
    <section class="container max-w-7xl mx-auto mt-28 md:mt-32 lg:mt-40">
      <div class="max-w-2xl mx-auto flex items-center justify-center flex-col text-center mb-8">
        <h1 class="text-3xl lg:text-4xl lg:max-w-sm leading-tight font-bold mb-5 font-Raleway">
          Designs with finesse, We make it impress!
        </h1>
        <p class="font-Poppins font-light leading-relaxed">
          Design with Ambillah. We’ll take your users from a great first impression up until
          purchase. We transform first impressions into lasting conversions. Build a strong brand
          identity with AMBILLAH
        </p>
      </div>
      <div>
        <Vue3Marquee>
          <figure>
            <img alt="" src="/images/img_4.png" />
          </figure>
        </Vue3Marquee>
      </div>
    </section>
    <!--  Projects  -->

    <!--  Services  -->
    <ServiceSection id="services" />
    <!--  Services  -->

    <!--  CTA  -->
    <section class="container max-w-7xl mx-auto bg-[#141414]">
      <div class="flex flex-col items-center gap-10 mt-32 sm:flex-row">
        <div
          class="max-w-2xl mx-auto flex items-center md:items-start text-center md:text-start justify-center flex-col"
        >
          <h1 class="text-4xl max-w-sm leading-tight font-bold mb-5 font-Raleway">
            Great interface for great interaction!
          </h1>
          <p class="font-Poppins font-light mb-12 leading-relaxed">
            With Ambillah, create a great interface to drive great interactions, leading to
            conversions. How do you want your site to shine?
          </p>
          <Button
            class="bg-transparent hover:bg-transparent border border-white font-Poppins font-light"
          >
            <a href="https://forms.gle/RRYYKr4jBF7uyz3Y8" rel="noopener noreferrer" target="_blank">
              Book a free consultation.
            </a>
          </Button>
        </div>
        <figure>
          <img alt="" src="/images/img_9.png" />
        </figure>
      </div>
    </section>
    <!--  CTA  -->

    <MarqueeSlider />
  </main>
</template>

<style scoped></style>
