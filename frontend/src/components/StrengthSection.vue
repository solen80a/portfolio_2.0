<script setup>
import { ref } from 'vue';

const strengths = ref([
  'Strong problem-solving skills',
  'Excellent communication abilities',
  'Proficient in multiple programming languages',
  'Ability to work well in teams',
  'Branding',
  'Strategy',
  'Process Design',
  'Concept',
  'Development',
  'Agile methodology',
  'Team work',
  'Problem Solving',
  'Adaptability',
  'Communication',
]);
</script>

<template>
  <div class="border-l-4 border-gray-500">
  <div class="flex justify-center items-center p-6 bg-gray-100">
    <h2 class="text-2xl font-bold">Strengths</h2>
  </div>
    <ul class="flex flex-col flex-wrap gap-2 bg-gray-100 p-4">
      <li v-for="strength in strengths" :key="strength">{{ strength }}</li>
    </ul>
 
  </div>
</template>
