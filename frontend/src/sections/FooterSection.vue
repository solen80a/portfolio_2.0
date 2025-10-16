<script setup>
import { Github, Linkedin, FileText, FileDown } from 'lucide-vue-next';

</script>

<template>
  <footer id="footer-section" class="flex items-center justify-evenly m-2 md:m-4 p-4 md:p-8 bg-main rounded-xl shadow-md  min-w-80 max-w-400">    
    <a href="sofialennbom@gmail.com" class=" hover:text-main-accent">©2025 Sofia Lennbom</a> 
    <div class="flex justify-center px-4 space-x-4">
      <a 
        href="https://www.linkedin.com/in/sofia-lennbom-91252195/" 
        target="_blank" 
        rel="icon"
        title="Open LinkedIn"  
        class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">     
        <Linkedin class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors" />
      </a>

      <a 
        href="https://github.com/solen80a" 
        target="_blank" 
        rel="icon"
        title="Open Github" 
        class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">     
          <Github class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors" />
      </a>

      <a 
        href="/assets/Sofia_Lennbom_CV.pdf"
        download="Sofia _Lennbom_CV"
        rel="icon"
        title="Download CV" 
        class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">
        <FileText class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors"/>
      </a>

      <!-- <a 
        href="https://github.com/solen80a" 
        target="_blank" 
        rel="noopener noreferrer"
        class="flex items-center"
      >
        <img 
          src="/assets/github-mark.png" 
          alt="GitHub icon" 
          class="w-4 md:w-8 h-4 md:h-8 hover:text-main-accent hover:opacity-80 transition-all" 
        />
        
      </a>
      
      <a 
        href="http://linkedin.com/in/sofia-lennbom" 
        target="_blank" 
        rel="noopener noreferrer"
        class="flex items-center"
      >
        <img 
          src="/assets/LinkedIn-Black.png" 
          alt="LinkedIn icon" 
          class="w-4 md:w-8 h-4 md:h-8 hover:text-main-accent hover:opacity-80 transition-all" 
        />        
      </a> 

      <a href="CV.pdf" class=" hover:text-main-accent">
      <FileText class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors"/>
      </a> -->

      
    </div>

  </footer>
</template>