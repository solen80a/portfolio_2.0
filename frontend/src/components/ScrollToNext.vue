<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isAtLastSection = ref(false)

const updateArrowDirection = () => {
  const sections = [
    document.getElementById("header-section"),
    document.getElementById("project-section"), 
    document.getElementById("skills-section"),
    //document.getElementById("footer-section")
  ]
  
  const currentScroll = window.scrollY
  let currentSectionIndex = 0
  
  // Find which section we're currently viewing
  for (let i = 0; i < sections.length; i++) {
    if (sections[i]) {
      const sectionTop = sections[i].offsetTop
      const sectionHeight = sections[i].offsetHeight
      
      if (currentScroll >= sectionTop - 100 && currentScroll < sectionTop + sectionHeight - 100) {
        currentSectionIndex = i
        break
      }
    }
  }
  
  // Check if we're at the last section
  isAtLastSection.value = currentSectionIndex === sections.length - 1
}

const scrollToNext = () => {
  const sections = [
    document.getElementById("header-section"),
    document.getElementById("project-section"), 
    document.getElementById("skills-section"),
    //document.getElementById("footer-section")
  ]
  
  const currentScroll = window.scrollY
  let currentSectionIndex = 0
  
  // Find which section we're currently viewing
  for (let i = 0; i < sections.length; i++) {
    if (sections[i]) {
      const sectionTop = sections[i].offsetTop
      const sectionHeight = sections[i].offsetHeight
      
      if (currentScroll >= sectionTop - 100 && currentScroll < sectionTop + sectionHeight - 100) {
        currentSectionIndex = i
        break
      }
    }
  }
  
  // Scroll to next section
  const nextIndex = currentSectionIndex + 1
  if (nextIndex < sections.length && sections[nextIndex]) {
    console.log(`Scrolling from section ${currentSectionIndex} to section ${nextIndex}`)
    sections[nextIndex].scrollIntoView({ 
      behavior: "smooth", 
      block: "start" 
    })
  } else {
    // If we're at the last section, scroll back to top
    console.log("At last section, scrolling to top")
    window.scrollTo({
      top: 0,
      behavior: "smooth"
    })
  }
  
  // Update arrow direction after a short delay
  setTimeout(updateArrowDirection, 500)
}

onMounted(() => {
  // Set initial arrow direction
  updateArrowDirection()
  // Listen for scroll events to update arrow direction
  window.addEventListener('scroll', updateArrowDirection)
})

onUnmounted(() => {
  window.removeEventListener('scroll', updateArrowDirection)
})
</script>

<template>
  <div class="fixed bottom-6 left-1/2 -translate-x-1/2 z-50 px-8">
    <button 
      @click="scrollToNext"
      class="bg-main-accent hover:bg-main-text text-main-text hover:text-main-light p-4 rounded-full shadow-lg transition-colors duration-300"
      :aria-label="isAtLastSection ? 'Scroll to top' : 'Scroll to next'"
    >
      <!-- Down arrow (default) -->
      <svg 
        v-if="!isAtLastSection" 
        class="w-6 h-6 transition-transform duration-300" 
        fill="none" 
        stroke="currentColor" 
        viewBox="0 0 24 24"
      >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v18m-7-7l7 7m0 0l7-7" />
      </svg>

      <!-- Up arrow (when at last section) -->
      <svg 
        v-else 
        class="w-6 h-6 transition-transform duration-300" 
        fill="none" 
        stroke="currentColor" 
        viewBox="0 0 24 24"
      >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 10l7-7m0 0l7 7m-7-7v18" />
      </svg>
    </button>
  </div>
</template>