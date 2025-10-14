<script setup>
import { Github, Linkedin, FileText } from 'lucide-vue-next';

// export default {
//   name: 'ContactSection',
// }
</script>

<template>
  <div class="flex flex-col items-start justify-center py-4 md:py-8 px-2 md:px-4 space-y-4 mb-4 md:max-w-400 md:mx-auto ">
    <h2 class="font-family-rubik text-2xl md:text-4xl font-bold">Let´s Talk</h2>     
    <div class="flex flex-col space-y-2">
      <a href= "+46705623461" class=" hover:text-gray-900">+46(0)705 62 34 61</a> 
      <a href="sofialennbom@gmail.com" class=" hover:text-main-accent">sofialennbom@gmail.com</a> 
    </div>
    <div class="flex justify-center items-center space-x-4">
      <a 
        href="https://www.linkedin.com/in/sofia-lennbom-91252195/" 
        target="_blank" 
        rel="noopener noreferrer" 
        class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">
           <!--  <img 
          src="/assets/LinkedIn-Black.png" 
          alt="LinkedIn icon" 
          class="w-8 h-8  hover:text-main-accent hover:opacity-80 transition-all" 
        /> -->
        <Linkedin class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors" />
      </a>
      <a href="https://github.com/solen80a" target="_blank" rel="noopener noreferrer"
         class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">
        <!-- <img 
          src="/assets/github-mark.png" 
          alt="GitHub icon" 
          class="w-8 h-8  hover:text-main-accent hover:opacity-80 transition-all" 
        /> -->
          <Github class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors" />
      </a>
      <a 
        href="/assets/Sofia_Lennbom_CV.pdf"
        download="Sofia _Lennbom_CV"
        class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">
        <FileText class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors"/>
      </a>
    </div>  
  </div>
</template>