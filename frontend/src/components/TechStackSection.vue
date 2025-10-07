<script setup>
import { ref } from 'vue';

const techStack = ref([
  'JavaScript ES6',
  'HTML5',
  'CSS3',
  'Styled components',
  'React',
  'Vue.js',
  'GitHub',
  'Bitbucket',
  'Jenkins',
  'MSSQL',
  'MongoDB',
  'Node.js',
  'Express.js',
  'RESTful APIs',
  'Version control with Git',
  'CI/CD pipelines',
  'Figma',
  'Slack',
  'Jira',
  'Confluence',
  'Office 365',
  'Responsive design',
  'Cross-browser compatibility',
]);
</script>

<template>
  <div class="flex justify-center items-center p-6 bg-gray-100">
    <h2 class="text-2xl font-bold">Technical</h2>
  </div>

  <ul class="flex flex-col flex-wrap gap-2 p-4 bg-gray-100">
    <li v-for="skill in techStack" :key="skill">{{ skill }}</li>
  </ul>
</template>
