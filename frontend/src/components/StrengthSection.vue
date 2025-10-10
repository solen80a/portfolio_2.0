<script setup>
import { ref } from 'vue';

const strengths = ref([
  'Strong problem-solving skills',
  'Excellent communication abilities',
  'Proficient in multiple programming languages',
  'Ability to work well in teams',
  'Quick learner',
  'Attention to detail',
  'Time management',
  'Creativity',
  'Critical thinking',
  'Agile methodology',    
  'Adaptability',
  'Responsive design',
  'Cross-browser compatibility',
  'Accessibility best practices',
  
]);
</script>

<template>
  <div class="border-l-4 border-main-accent">
  <div class="flex justify-center items-center p-4 md:p-8">
    <h2 class="text-2xl font-bold">Strengths</h2>
  </div>
    <ul class="flex flex-col flex-wrap md:gap-2 p-2 md:p-4">
      <li v-for="strength in strengths" :key="strength">{{ strength }}</li>
    </ul>
 
  </div>
</template>
