<script>
import AboutSection from './AboutSection.vue';
import ContactSection from './ContactSection.vue';

export default {
  name: 'HeaderSection',
  components: {
    AboutSection,
    ContactSection
  }}
  
</script>

<template>
  <div class="header flex items-center justify-center min-h-screen py-2">
    <AboutSection />
    <ContactSection />
  </div>
</template>