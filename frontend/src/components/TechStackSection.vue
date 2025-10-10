<script setup>
import { ref } from 'vue';

const techStack = ref([
  'JavaScript ES6',
  'HTML5',
  'CSS3',
  'Styled components',
  'Tailwind CSS',
  'React',
  'Vue.js',
  'Version control with Git',
  'GitHub',
  'Bitbucket',
  'Jenkins',
  'MSSQL',
  'MongoDB',
  'Node.js',
  'Express.js',
  'RESTful APIs',    
  'Figma',
  'Slack',
  'Jira',
  'Confluence',
  'Office 365',
]);
</script>

<template>
  <div class="md:border-l-4 md:border-main-accent">
    <div class="flex justify-center items-center p-4 md:p-8">
      <h2 class="text-2xl font-bold">Technical</h2>
    </div>

    <ul class="flex flex-col flex-wrap p-2 md:p-4">
      <li v-for="skill in techStack" :key="skill">{{ skill }}</li>
    </ul>
  </div>
</template>
