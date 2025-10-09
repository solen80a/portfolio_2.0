<script setup>
import HeaderSection from './components/HeaderSection.vue';
import FooterSection from './components/FooterSection.vue';
import ProjectsSection from './components/ProjectsSection.vue';
import ScrollToNext from './components/ScrollToNext.vue';
import TopArrow from './components/TopArrow.vue';
import SkillsSection from './components/SkillsSection.vue';
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



