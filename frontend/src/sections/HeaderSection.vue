<script>
import AboutSection from '../components/AboutSection.vue';
import ContactSection from '../components/ContactSection.vue';

export default {
  name: 'HeaderSection',
  components: {
    AboutSection,
    ContactSection
  }}
  
</script>

<template>
  <header id="header-section" class="flex flex-col md:flex-row justify-evenly items-start py-1 md:py-2 min-w-80 md:max-w-400 bg-main shadow-md space-y-4 rounded-xl m-2 md:m-4">     
    <AboutSection />
    <ContactSection />  
  </header> 
</template>