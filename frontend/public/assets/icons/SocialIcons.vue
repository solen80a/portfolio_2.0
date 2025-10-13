<script setup>
import { Github, Linkedin, FileText, Globe } from 'lucide-vue-next'
</script>

<template>
  <div class="flex space-x-4">
    <!-- GitHub -->
    <a href="https://github.com/solen80a" class="text-main hover:text-main-accent transition-colors">
      <Github :size="24" />
    </a>
    
    <!-- LinkedIn -->
    <a href="https://linkedin.com/in/yourprofile" class="text-main hover:text-main-accent transition-colors">
      <Linkedin :size="24" />
    </a>
    
    <!-- CV/Resume -->
    <a href="/path-to-your-cv.pdf" class="text-main hover:text-main-accent transition-colors">
      <FileText :size="24" />
    </a>
    
    <!-- Website/Portfolio -->
    <a href="https://yourwebsite.com" class="text-main hover:text-main-accent transition-colors">
      <Globe :size="24" />
    </a>
  </div>
</template>