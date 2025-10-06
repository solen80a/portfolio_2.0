<script setup>
import { ref, onMounted, nextTick } from 'vue'
import 'vue3-carousel/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import projects from '../data/projects.json'

const projectsList = projects.projects // All projects
const isCarouselReady = ref(false)

// Prevent initial carousel strobing
onMounted(async () => {
  // Wait for DOM to fully settle
  await nextTick()
  // Minimal delay for smooth initialization
  setTimeout(() => {
    isCarouselReady.value = true
  }, 100)
})

const config = {
  itemsToShow: 2.5,
  wrapAround: false, // true made it strobe???
  autoplay: 0,
  transition: 300,
  gap: 20,
  mouseDrag: true,
  touchDrag: true,
  snapAlign: 'start'
}
</script>

<template>
  <div class="carousel-container p-6">
    <!-- Loading state to prevent initial strobing -->
    <div v-if="!isCarouselReady" class="flex justify-center items-center" style="height: 400px;">
      <div class="text-gray-500">Loading carousel...</div>
    </div>
    
    <!-- Carousel renders only when ready -->
    <Carousel v-else v-bind="config">
      <Slide v-for="(project, index) in projectsList" :key="index">
        <div class="bg-white rounded-xl shadow-lg overflow-hidden" style="height: 400px; width: 100%;">
          <!-- Image Section -->
          <div 
            style="
              height: 200px; 
              background: linear-gradient(45deg, #f3f4f6, #e5e7eb); 
              overflow: hidden;
              position: relative;
            "
          >
            <img 
              :src="project.image" 
              :alt="project.name" 
              style="
                width: 100%; 
                height: 100%; 
                object-fit: cover; 
                position: absolute;
                top: 0;
                left: 0;
              "
              loading="lazy"
              decoding="async"
            />
            
            <!-- Community badge -->
            <img 
              v-if="project.community"
              :src="project.community" 
              :alt="project.communityname || 'Community'" 
              style="
                position: absolute;
                bottom: 8px;
                right: 8px;
                width: 32px;
                height: 32px;
                border-radius: 50%;
                object-fit: cover;
                border: 2px solid white;
                box-shadow: 0 1px 3px rgba(0,0,0,0.1);
              "
              loading="lazy"
            />
          </div>
          
          <!-- Content Section -->
          <div class="p-6">
            <h3 class="text-xl font-bold text-gray-800 mb-3 line-clamp-2">{{ project.name }}</h3>
            <p class="text-gray-600 text-sm leading-relaxed line-clamp-3">{{ project.content }}</p>
          </div>
        </div>    
      </Slide>  
       
      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
  </div>
</template>

<style>
/* Custom CSS Variables for vue3-carousel (can't be converted to Tailwind) */
.carousel-container .carousel {
  --vc-pgn-background-color: rgba(255, 255, 255, 0.9);
  --vc-pgn-active-color: rgba(59, 130, 246, 1);
  --vc-nav-background: rgba(255, 255, 255, 0.9);
  --vc-nav-border-radius: 100%;
}

/* Line clamp utilities for text truncation */
/* .line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.line-clamp-4 {
  display: -webkit-box;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
  overflow: hidden;
} */
</style>
