<script setup>
import ProjectCarousel from './ProjectCarousel.vue';
</script>

<template>
  <section id="project-section" class="flex flex-col justify-center items-center min-h-screen m-2 md:m-4 p-4 md:p-8 bg-main rounded-xl shadow-md min-w-80 max-w-400">
    <h2 class="text-2xl font-bold mb-4">Featured Projects</h2>
    <ProjectCarousel />
  </section>
</template>