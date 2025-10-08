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
  itemsToShow: 1.25, // Default for mobile
  wrapAround: false, // true made it strobe???
  autoplay: 0,
  transition: 300,
  gap: 20,
  mouseDrag: true,
  touchDrag: true,
  snapAlign: 'start',
  // Responsive breakpoints
  breakpoints: {
    // 640px and up (sm): show 1.5 items
    640: {
      itemsToShow: 1.5,
      gap: 16
    },
    // 768px and up (md): show 2 items  
    768: {
      itemsToShow: 2.5,
      gap: 20
    }    
  }
}
</script>

<template>
  <div class="carousel-container m-2 md:m-4 p-4 md:p-8 min-w-80 max-w-400 mx-auto w-full">
    <!-- Loading state to prevent initial strobing -->
    <div v-if="!isCarouselReady" class="flex justify-center items-center" style="height: 400px;">
      <div class="text-main-text">Loading carousel...</div>
    </div>
    
    <!-- Carousel renders only when ready -->
    <Carousel v-else v-bind="config">
      <Slide v-for="(project, index) in projectsList" :key="index">
        <div class="bg-main border-2 border-main-text rounded-xl shadow-lg overflow-hidden" style="height: 400px; width: 100%;">
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
          <div class="bg-main m-2 md:m-4 p-4 md:p-8">
            <h3 class="text-xl font-bold mb-3 line-clamp-2">{{ project.name }}</h3>
            <p class="md:text-sm leading-relaxed line-clamp-3">{{ project.content }}</p>
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
  --vc-pgn-background-color: #EBEBEB;
  --vc-pgn-active-color: #292828;
  --vc-nav-background: #EBEBEB;
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
