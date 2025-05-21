<template>
    <section class="relative h-screen flex items-end overflow-hidden">
        <!-- Vidéo en arrière-plan -->
        <video autoplay muted loop playsinline class="absolute top-0 left-0 w-full h-full object-cover">
            <source :src="video" type="video/mp4" />
            Your browser does not support the video tag.
        </video>

        <!-- Overlay + Contenu -->
        <div class="relative z-10 w-full text-white bg-gradient-to-t from-neutral-900 to-transparent p-8 md:p-16">
            <FadeInOnScroll>
                <h1 class="text-4xl md:text-7xl lora-font">Rayol Horizon</h1>
                <p class="mt-4 text-lg md:text-2xl font-thin">
                    Un cocon paisible à deux pas de la mer, au cœur du Rayol-Canadel-sur-Mer
                </p>
            </FadeInOnScroll>
        </div>
    </section>
</template>

<script setup>
import FadeInOnScroll from '@/components/FadeInOnScroll.vue'
import videoFile from '../assets/Design sans titre-3.mp4'
const video = videoFile
</script>

<style scoped>
.lora-font {
    font-family: 'Lora', serif;
}
</style>
