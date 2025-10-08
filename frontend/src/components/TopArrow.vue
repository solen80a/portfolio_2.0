<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const visible = ref(false)

const toggleVisibility = () => {
  if (window.scrollY > 300) {
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
  <div v-if="visible" class="fixed bottom-6 left-1/2 -translate-x-1/2 z-50">
    <button
      @click="scrollToTop"
      class="bg-main-accent shadow-lg rounded-full p-4 hover:bg-main-light transition-colors"
    >
      <!-- Arrow Up Circle Icon - Exchange for a icon library later -->
      <svg
        class="h-6 w-6"
        fill="currentColor"
        viewBox="0 0 24 24"
      >
        <path
          fill-rule="evenodd"
          d="M12 2.25c-5.385 0-9.75 4.365-9.75 9.75s4.365 9.75 9.75 9.75 9.75-4.365 9.75-9.75S17.385 2.25 12 2.25zm.53 5.47a.75.75 0 00-1.06 0l-3 3a.75.75 0 101.06 1.06L12 9.31l2.47 2.47a.75.75 0 101.06-1.06l-3-3z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
  </div>
</template>

<style scoped>
/* Add any component-specific styles here if needed */
</style>