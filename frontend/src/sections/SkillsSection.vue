<script setup>
import StrengthSection from '../components/StrengthSection.vue';
import TechStackSection from '../components/TechStackSection.vue';

</script>

<template>
  <section id="skills-section" class="flex justify-evenly items-start bg-main rounded-xl shadow-md m-2 md:m-4 p-4 md:p-8 min-w-80 md:max-w-400">
    <TechStackSection />
    <StrengthSection />   
  </section>
</template>
