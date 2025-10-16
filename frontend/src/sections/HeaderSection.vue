<script setup>
import AboutSection from '../components/AboutSection.vue';
import ContactSection from '../components/ContactSection.vue';  
</script>

<template>
  <header id="header-section" 
  class="flex flex-col md:flex-row justify-evenly items-start min-w-80 md:max-w-400 bg-main rounded-xl shadow-md space-y-4 py-1 md:py-2 m-2 md:m-4">     
    <AboutSection />
    <ContactSection />  
  </header> 
</template>