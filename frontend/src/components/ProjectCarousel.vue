<script setup>

import 'vue3-carousel/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import projects from '../data/projects.json'

const projectsList = projects.projects


// Add my projects and img
// const images = Array.from({ length: 10 }, (_, index) => ({
//   id: index + 1,
//   url: `https://picsum.photos/seed/${Math.random()}/800/600`,
// }))

// const projectsData = ProjectsSection.projects(name, images, tags, content , netlify, github, community); 

const config = {
  itemsToShow: 2.5,
  wrapAround: true,
  height: 200,  
  gap: 5,
}
</script>

<template>
  <Carousel v-bind="config">
    <Slide v-for="project in projectsList" :key="project.name">
      <!-- <h2>"project.name"</h2> -->
      <img :src="project.image" :alt="project.name" />
    </Slide>
     
     <!-- Example slides using placeholder images -->
    <!-- <Slide v-for="image in images" :key="image.id">
      <img :src="image.url" alt="image" />
    </Slide> -->

    <template #addons>
      <Navigation />
      <Pagination />
    </template>
  </Carousel>

</template>

<!-- Move styling to Tailwind CSS -->
<style>
.carousel {
  --vc-pgn-background-color: rgba(255, 255, 255, 0.7);
  --vc-pgn-active-color: rgba(255, 255, 255, 1);
  --vc-nav-background: rgba(255, 255, 255, 0.7);
  --vc-nav-border-radius: 100%;
}

img {
  border-radius: 8px;
  width: 100%;
  height: 100%;
  object-fit: cover;
} 
</style>
