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
  <header class="flex justify-evenly items-start py-2 max-w-400 bg-gray-100 shadow-md space-y-4 rounded-xl m-4">     
    <AboutSection />
    <ContactSection />  
  </header> 
</template>