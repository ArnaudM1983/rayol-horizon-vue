<template>
  <Navbar />

  <main class="bg-neutral-900 mx-auto space-y-20">
    <Hero />
    <Images />
    <Marquee />
    <ImageTextSection />
    <FullWidthSlider />
    <Map />
    <Equipement />
    <Banner />
    <QuestionsFrequentes />
    <ScrollingBanner />

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
import Marquee from './components/Marquee.vue'
import ImageTextSection from './components/ImageTextSection.vue'
import FullWidthSlider from './components/FullWidthSlider.vue'
import Map from './components/Map.vue'
import Equipement from './components/Equipement.vue'
import Banner from './components/Banner.vue'
import QuestionsFrequentes from './components/QuestionsFrequentes.vue'
import ScrollingBanner from './components/ScrollingBanner.vue'
</script>
