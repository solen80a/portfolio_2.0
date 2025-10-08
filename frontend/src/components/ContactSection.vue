<script>
// import { CodeBracketIcon } from "@heroicons/vue/24/outline" // If you need icons

export default {
  name: 'ContactSection',
}
</script>

<template>
  <div class="flex flex-col items-start justify-center py-8 px-4 space-y-4 max-w-400 mx-auto">
    <h2 class="text-2xl font-bold ">Let´s Talk</h2>     
    <ul class="space-y-2">
      <li>
        <a href= "+46705623461" class=" hover:text-gray-900">+46(0)705 62 34 61</a>
      </li>
      <li>
        <a href="sofialennbom@gmail.com" class=" hover:text-main-accent">sofialennbom@gmail.com</a> 
      </li>
      </ul>
      <ul class="flex justify-center items-center space-x-4">
      <li>
        <a href="https://www.linkedin.com/in/sofia-lennbom-91252195/" target="_blank" rel="noopener noreferrer">
          <img 
          src="/assets/LinkedIn-Black.png" 
          alt="LinkedIn icon" 
          class="w-8 h-8  hover:text-main-accent hover:opacity-80 transition-all" 
        /></a>
        <!-- Fix icons to hover accent color -->
      </li>
      <li>        
        <a href="https://github.com/solen80a" target="_blank" rel="noopener noreferrer">
        <img 
          src="/assets/github-mark.png" 
          alt="GitHub icon" 
          class="w-8 h-8  hover:text-main-accent hover:opacity-80 transition-all" 
        />
        </a>
      </li>
      <li>
        <a href="CV.pdf" class="hover:text-main-accent">CV</a>
      </li>
    </ul>  
  </div>
     
      
</template>