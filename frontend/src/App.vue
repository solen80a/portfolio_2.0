<script setup>
import HeaderSection from './components/HeaderSection.vue';
import FooterSection from './components/FooterSection.vue';
import ProjectsSection from './components/ProjectsSection.vue';
import ScrollToTop from './components/ScrollToTop.vue';
import TopArrow from './components/TopArrow.vue';
</script>

<template>
  <div id="app" class="min-h-screen flex flex-col justify-items-center">
    <HeaderSection />
    <main class="flex-grow">
      <ProjectsSection />

      <!-- decide on top arrow -->
      <ScrollToTop />
      <TopArrow />
      <!--  -->
      
    </main>
      <FooterSection />
  </div>
</template>



