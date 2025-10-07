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
  <header class="flex justify-evenly items-center py-2 max-w-400 mx-auto rounded-lg bg-gray-100 shadow-md space-y-4">     
    <AboutSection />
    <ContactSection />  
  </header> 
</template>