<template>
    <section
      class="mt-36 overflow-hidden whitespace-nowrap bg-neutral-900 text-white py-8 border-t border-b border-white"
    >
      <div
        ref="marquee"
        class="inline-block"
        :style="{ transform: `translateX(${offset}px)` }"
      >
        <span class="mx-10 text-3xl md:text-6xl font-light">VUE MER</span>
        <span class="mx-10 text-3xl md:text-6xl">PLAGE PROCHE</span>
        <span class="mx-10 text-3xl md:text-6xl">DÉCOR SOIGNÉ</span>
        <span class="mx-10 text-3xl md:text-6xl font-light">VUE MER</span>
        <span class="mx-10 text-3xl md:text-6xl">PLAGE PROCHE</span>
        <span class="mx-10 text-3xl md:text-6xl">DÉCOR SOIGNÉ</span>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref, onMounted, onUnmounted } from "vue";
  
  const offset = ref(0);
  const marquee = ref(null);
  let width = 0;
  
  let lastScrollY = window.scrollY;
  let animationFrameId;
  
  const handleScroll = () => {
    const currentY = window.scrollY;
    const delta = currentY - lastScrollY;
  
    offset.value -= delta * 0.5; // ajuster la sensibilité au scroll ici
    lastScrollY = currentY;
  
    // limiter l'offset pour éviter d'aller trop loin dans un sens (optionnel)
    if (offset.value > 0) offset.value = 0;
  };
  
  const animate = () => {
    offset.value -= 0.8; // vitesse auto scroll
  
    // Remise à zéro quand décalage dépasse la moitié (pour boucle)
    if (Math.abs(offset.value) >= width / 2) {
      offset.value += width / 2; // repositionner vers la droite pour boucle fluide
    }
  
    animationFrameId = requestAnimationFrame(animate);
  };
  
  onMounted(() => {
    width = marquee.value.offsetWidth;
    window.addEventListener("scroll", handleScroll);
    animate();
  });
  
  onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll);
    cancelAnimationFrame(animationFrameId);
  });
  </script>
  
  <style scoped>
  span {
    font-family: "urbanist", sans-serif;
    font-weight: 100;
  }
  
  /* Pour lisser le mouvement */
  section {
    will-change: transform;
  }
  </style>
  