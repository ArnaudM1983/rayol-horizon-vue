<template>
  <Navbar />

  <main class="bg-neutral-900 mx-auto space-y-32">
    <Hero />

    <section id="images"
      class="min-h-screen bg-neutral-900 flex items-center justify-center max-w-[1250px] mx-auto w-full">
      <Images />
    </section>

    <section id="services" class="min-h-screen bg-gray-100 flex items-center justify-center">
      <h1 class="text-4xl font-bold">Services</h1>
    </section>

    <section id="contact" class="min-h-screen bg-gray-200 flex items-center justify-center">
      <h1 class="text-4xl font-bold">Contact</h1>
    </section>
  </main>
</template>

<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Images from './components/Images.vue'
</script>
