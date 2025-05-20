<template>
  <header class="absolute top-0 mt-2 left-0 w-full z-50 bg-transparent text-white">

    <div class="flex justify-between items-center p-6 lg:px-12">

      <!-- Mobile Toggle Button -->
      <div class="md:hidden z-30">
        <button @click="isMenuOpen = !isMenuOpen" class="text-3xl text-red-500">
          <Icon :icon="isMenuOpen ? 'material-symbols:close' : 'material-symbols:menu'" />
        </button>
      </div>

      <!-- Nav Links -->
      <nav :class="[
        'absolute md:static left-0 top-full w-full md:w-auto bg-white md:bg-transparent p-6 md:p-0 shadow-md md:shadow-none',
        'flex flex-col md:flex-row items-center gap-6 md:gap-16',
        isMenuOpen ? 'flex' : 'hidden',
        'md:flex'
      ]">
        <a href="#lappartement" @click.prevent="scrollToSection('#home')"
        class="relative text-white font-light uppercase text-xl after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-[1px] after:bg-white after:transition-all after:duration-300 hover:after:w-full">L'Appartement</a>
        <a href="#equipements" @click.prevent="scrollToSection('#about')"
        class="relative text-white font-light uppercase text-xl after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-[1px] after:bg-white after:transition-all after:duration-300 hover:after:w-full">Equipements</a>
        <a href="#faq" @click.prevent="scrollToSection('#services')"
        class="relative text-white font-light uppercase text-xl after:content-[''] after:absolute after:left-0 after:-bottom-1 after:w-0 after:h-[1px] after:bg-white after:transition-all after:duration-300 hover:after:w-full">FAQ</a>
      </nav>

      <!-- Logo -->
      <!-- <div class="text-3xl text-red-500 font-bold">LOGO</div> -->

      <!-- Réserver Button -->
      <button class="text-white border border-white px-6 py-2 text-lg font-light cursor-pointer bg-transparent rounded-none hover:bg-white hover:text-black transition">
        Réserver
      </button>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import { Icon } from '@iconify/vue'

const isMenuOpen = ref(false)

const scrollToSection = (id) => {
  isMenuOpen.value = false
  const section = document.querySelector(id)
  if (section) section.scrollIntoView({ behavior: 'smooth' })
}
</script>