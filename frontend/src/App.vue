<script setup>
import HeaderSection from './sections/HeaderSection.vue';
import FooterSection from './sections/FooterSection.vue';
import ProjectsSection from './sections/ProjectsSection.vue';
import ScrollToNext from './components/ScrollToNext.vue';
import TopArrow from './components/TopArrow.vue';
import SkillsSection from './sections/SkillsSection.vue';
</script>

<template>
  <div id="app" class="min-h-screen flex flex-col justify-items-center">
    <HeaderSection />
    <ScrollToNext />
    <main class="flex-grow">
      <ProjectsSection />
      <ScrollToNext />
      <SkillsSection />
      <ScrollToNext />
      <!-- decide on top arrow -->
      
      <!-- <TopArrow /> -->
      <!--  -->

    </main>
      <FooterSection />
  </div>
</template>



