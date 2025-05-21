
<template>
  
  <div class="relative overflow-hidden">
    <div class="wrapper" ref="wrapper">
      <section v-for="(slide, i) in slides" :key="i" class="panel relative">
        <div class="w-full h-full p-10 relative">
          <img :src="slide.image" class="w-full h-full object-cover shadow-lg" />
          <!-- Overlay gradient -->
          <div class="absolute bottom-0 left-0 w-full h-[40%] bg-gradient-to-t from-neutral-900 to-transparent z-10"></div>
          <!-- Text bottom left -->
          <div class="absolute left-24 bottom-24 text-white text-xl md:text-4xl font-light lora-font z-20">
            {{ slide.leftText }}
          </div>
          <!-- Text bottom right -->
          <div class="absolute bottom-24 right-24 text-white text-xl md:text-3xl font-light z-20">
            {{ slide.rightText }}
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref, nextTick } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
import FadeInOnScroll from '@/components/FadeInOnScroll.vue'

import plage from '../assets/chambre.png'
import cuisine from '../assets/cuisine.png'
import terrasse2 from '../assets/terrasse2.png'

gsap.registerPlugin(ScrollTrigger)

const wrapper = ref(null)
const slides = [
  { image: plage, leftText: 'Chambre Principale', rightText: '15m2' },
  { image: cuisine, leftText: 'Cuisine', rightText: '' },
  { image: terrasse2, leftText: 'Terrasse', rightText: '20m2' },
]

onMounted(async () => {
  await nextTick()

  const sections = wrapper.value.querySelectorAll('.panel')

  gsap.to(sections, {
    xPercent: -100 * (sections.length - 1),
    ease: 'none',
    scrollTrigger: {
      trigger: wrapper.value,
      pin: true,
      scrub: 0.5,
      snap: 1 / (sections.length - 1),
      start: 'top top',
      end: () => "+=" + wrapper.value.offsetWidth,
    },
  })
})
</script>

<style scoped>
.wrapper {
  display: flex;
  width: 400vw; /* 4 sections * 100vw */
  height: 100vh;
}

.panel {
  flex: 0 0 100vw;
  height: 100vh;
  position: relative;
}

.lora-font {
  font-family: 'Lora', serif;
}
</style>

