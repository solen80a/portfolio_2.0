<script>
import { CodeIcon } from "@vue-hero-icons/outline"

export default {
  name: 'ContactSection',
}
</script>

<template>
  <div class="flex flex-col items-start justify-center py-8 px-4 space-y-4 max-w-400 mx-auto">
    <h2 class="text-3xl font-bold">Let´s Talk</h2>     
    <ul class="space-y-2">
      <li>
        <a href= "+46705623461" class="text-gray-600 hover:text-gray-900">+46(0)705 62 34 61</a>
      </li>
      <li>
        <a href="sofialennbom@gmail.com" class="text-gray-600 hover:text-gray-900">sofialennbom@gmail.com</a> 
      </li>
      </ul>
      <ul class="flex justify-center items-center space-x-4">
      <li>
        <a href="https://www.linkedin.com/in/sofia-lennbom-91252195/" target="_blank" rel="noopener noreferrer">
          <img 
          src="https://linkedin.com/favicon.ico" 
          alt="LinkedIn icon" 
          class="w-8 h-8 hover:grayscale hover:opacity-80 transition-all" 
        /></a>
      </li>
      <li>        
        <a href="https://github.com/solen80a" target="_blank" rel="noopener noreferrer">
        <img 
          src="https://github.com/favicon.ico" 
          alt="GitHub icon" 
          class="w-8 h-8 hover:grayscale hover:opacity-80 transition-all" 
        />
        </a>
      </li>
      <li>
        <a href="CV.pdf" class="text-gray-600 hover:text-gray-900">CV</a>
      </li>
    </ul>  
  </div>
     
      
</template>