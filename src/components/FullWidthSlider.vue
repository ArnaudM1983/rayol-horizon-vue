<template>
  <section class="relative overflow-hidden max-w-[1250px] mx-auto">
    <h2 class="text-3xl mb-8 md:text-6xl font-semibold text-white sm:text-3xl text-left">
      Lumineux et accueillant
    </h2>

    <div class="relative h-[80vh] w-full overflow-hidden">
      <img
        :src="slides[currentSlide].image"
        alt="Slide image"
        class="object-cover w-full h-full transition-opacity duration-500"
      />

      <!-- Overlay -->
      <div class="absolute inset-0 bg-gradient-to-t from-neutral-900 to-transparent"></div>

      <!-- Captions -->
      <div class="absolute bottom-10 left-10 text-white text-xl md:text-4xl font-light lora-font">
        {{ slides[currentSlide].leftText }}
      </div>
      <div class="absolute bottom-10 right-10 text-white text-xl md:text-3xl font-light">
        {{ slides[currentSlide].rightText }}
      </div>

      <!-- Flèches de navigation -->
      <button
        @click="prevSlide"
        class="absolute left-4 top-1/2 -translate-y-1/2 bg-black/40 hover:bg-black/60 text-white p-2 rounded-full"
        aria-label="Slide précédent"
      >
        ◀
      </button>
      <button
        @click="nextSlide"
        class="absolute right-4 top-1/2 -translate-y-1/2 bg-black/40 hover:bg-black/60 text-white p-2 rounded-full"
        aria-label="Slide suivant"
      >
        ▶
      </button>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

// Import des images locales
import plage from '../assets/chambre.png'
import cuisine from '../assets/cuisine.png'
import terrasse2 from '../assets/terrasse2.png'

const slides = [
  { image: plage, leftText: 'Chambre Principale', rightText: '15m2' },
  { image: cuisine, leftText: 'Cuisine', rightText: '' },
  { image: terrasse2, leftText: 'Terrasse', rightText: '20m2' }
]

const currentSlide = ref(0)
let intervalId = null

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

const prevSlide = () => {
  currentSlide.value =
    (currentSlide.value - 1 + slides.length) % slides.length
}

onMounted(() => {
  intervalId = setInterval(nextSlide, 5000)
})

onUnmounted(() => {
  clearInterval(intervalId)
})
</script>

<style scoped>
.lora-font {
  font-family: 'Lora', serif;
}
</style>
