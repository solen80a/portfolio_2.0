<script setup>
import ProjectCarousel from './ProjectCarousel.vue';

import projects from '../data/projects.json'

const props = defineProps({
  name: String,
  image: String,
  tags: Array,
  content: String,
  netlify: String,
  github: String,
  netlifyIcon: String,
  netlifyAlt: String,
  netlifyTitle: String,
  githubIcon: String,
  githubAlt: String,
  githubTitle: String,
  community: Object
})


</script>

<template>
  <h2>Featured Projects</h2>
  <ProjectCarousel {...props} />
   
</template>