<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const visible = ref(false)

const toggleVisibility = () => {
  if (window.scrollY > 800) {
    visible.value = true
  } else {
    visible.value = false
  }
}

const scrollToTop = () => {
  window.scrollTo({
    top: 0,
    behavior: 'smooth'
  })
}

onMounted(() => {
  window.addEventListener('scroll', toggleVisibility)
})

onUnmounted(() => {
  window.removeEventListener('scroll', toggleVisibility)
})
</script>

<template>
  <div v-if="visible" class="fixed bottom-6 left-1/2 -translate-x-1/2 z-50 px-8">
    <button
      @click="scrollToTop"
      class="bg-main-accent shadow-lg rounded-full p-2 hover:bg-main-light transition-colors"
    >
      <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
      </svg>

    </button>
  </div>
</template>

<style scoped>
/* Add any component-specific styles here if needed */
</style>