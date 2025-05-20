<template>
    <section class="max-w-[1250px] mx-auto px-4 py-8">
      <div class="grid grid-cols-3 grid-rows-3 gap-4 text-white">
        <div
          v-for="(item, index) in pieces"
          :key="index"
          class="flex justify-between items-center border-b border-white py-4"
        >
          <span class="text-lg">{{ item.name }}</span>
          <span class="text-lg font-semibold">{{ item.value }}</span>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  const pieces = [
    { name: 'Chambre', value: 2 },
    { name: 'Salle de bain', value: 1 },
    { name: 'Cuisine', value: 1 },
    { name: 'Salon', value: 1 },
    { name: 'Terrasse', value: 1 },
    { name: 'Garage', value: 1 },
    { name: 'Bureau', value: 1 },
    { name: 'Toilettes', value: 2 },
    { name: 'Buanderie', value: 1 },
  ]
  </script>
  
  <style scoped>
  /* Optionnel : pour affiner l'apparence */
  </style>
  