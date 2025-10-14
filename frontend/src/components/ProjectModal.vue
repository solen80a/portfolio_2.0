<script setup>
import { Github, Globe } from 'lucide-vue-next'
import { ref } from 'vue'
import { Dialog, DialogPanel, DialogTitle, TransitionChild, TransitionRoot } from '@headlessui/vue'

// Props to receive the project data
const props = defineProps({
  project: {
    type: Object,
    required: true
  }
})

const open = ref(false)  

</script>

<template>
   <div> 
    <!-- <button class="rounded-md bg-main-accent px-2.5 py-1.5 text-sm font-semibold hover:bg-main-text hover:text-main-light" @click="open = true">Read more</button>  -->
    <button class="text-l font-semibold cursor-pointer" @click="open = true">Read more</button> 
    <TransitionRoot as="template" :show="open">
      <Dialog class="relative z-10" @close="open = false">
        <TransitionChild as="template" enter="ease-out duration-300" enter-from="opacity-0" enter-to="" leave="ease-in duration-200" leave-from="" leave-to="opacity-0">
          <div class="fixed inset-0 bg-gray-500/75 transition-opacity"></div>
        </TransitionChild>

        <div class="fixed inset-0 z-10 w-screen overflow-y-auto">
          <div class="flex min-h-full items-end justify-center p-4 text-center sm:items-center sm:p-0">
            <TransitionChild as="template" enter="ease-out duration-300" enter-from="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95" enter-to=" translate-y-0 sm:scale-100" leave="ease-in duration-200" leave-from=" translate-y-0 sm:scale-100" leave-to="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95">
              <DialogPanel class="relative transform overflow-hidden rounded-lg bg-main text-left shadow-xl transition-all sm:my-8 sm:w-full sm:max-w-lg">
                <div class="bg-main px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
                  <div class="sm:flex sm:items-start">               
                    <div class="mt-3 text-center sm:mt-0 sm:ml-4 sm:text-left">
                      <DialogTitle as="h3" class="text-xl font-semibold">{{ props.project.name }}</DialogTitle>
                      <div class="mt-2">
                        <p class="mb-4">{{ props.project.content }}</p>
                        
                        <!-- Project Links -->
                        <div class="flex space-x-3 justify-left">
                          <a :href="props.project.github" target="_blank" class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">
                            <Github class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors" />
                          </a>
                          <a :href="props.project.netlify" target="_blank" class="bg-main-accent rounded-full shadow-lg p-2 hover:bg-main-text transition-colors">
                            <Globe class="w-6 h-6 text-main-text hover:text-main-light hover:bg-main-text transition-colors" />
                          </a>
                        </div>
                        
                        <!-- Tags if available -->
                        <div v-if="props.project.tags" class="mt-4">
                          <p class="mb-2 text-lg font-semibold">Technologies:</p>
                          <div class="flex flex-wrap gap-2">
                            <!-- <span v-for="tag in props.project.tags" :key="tag" class="px-2 py-1 bg-main-accent rounded-full"> -->
                            <p v-for="tag in props.project.tags" :key="tag" class="px-2 py-1">
                              {{ tag }}
                            </p>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="bg-main px-4 py-3 sm:flex sm:flex-row-reverse sm:px-6">                
                  <button type="button" class="mt-3 inline-flex w-full justify-center rounded-md bg-main-accent px-3 py-2 font-semibold shadow-lg transition-colors hover:bg-main-text hover:text-main-light sm:mt-0 sm:w-auto" @click="open = false" ref="cancelButtonRef">Close</button>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </Dialog>
    </TransitionRoot>
  </div>
</template>