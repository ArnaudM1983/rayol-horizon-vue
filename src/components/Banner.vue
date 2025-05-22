<template>
    <section class="relative h-screen overflow-hidden">
      <div
        class="absolute inset-0 bg-center bg-cover parallax"
        :style="{ backgroundImage: `url('/terrasse2.png')` }"
      ></div>
    </section>
  </template>
  
  <style scoped>
  .parallax {
    background-attachment: fixed;
    background-size: cover;
    background-repeat: no-repeat;
  }
  </style>
  