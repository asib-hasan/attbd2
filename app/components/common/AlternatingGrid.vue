<template>
  <div class="py-20 md:py-32 bg-slate-950">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      
      <!-- Section Header -->
      <div v-if="title || description" class="text-center max-w-3xl mx-auto mb-20 md:mb-32">
        <h2 v-animate="'animate-fade-up'" class="text-3xl md:text-5xl font-bold text-white mb-6">
          <span v-if="highlight" class="text-blue-500">{{ highlight }}</span>
          {{ title }}
        </h2>
        <p v-if="description" v-animate="'animate-fade-up delay-100'" class="text-lg md:text-xl text-slate-400 leading-relaxed">
          {{ description }}
        </p>
      </div>

      <!-- Grid Items -->
      <div class="space-y-24 md:space-y-40">
        <div 
          v-for="(item, index) in items" 
          :key="index"
          :id="item.id"
          class="flex flex-col md:flex-row items-center gap-12 lg:gap-20"
          :class="{'md:flex-row-reverse': index % 2 !== 0}"
        >
          <!-- Image -->
          <div v-animate="index % 2 !== 0 ? 'animate-slide-left' : 'animate-fade-up'" class="w-full md:w-1/2">
            <div class="rounded-3xl overflow-hidden bg-slate-900 border border-slate-800 shadow-2xl">
              <img 
                :src="item.image" 
                :alt="item.title"
                class="w-full h-[350px] md:h-[500px] object-cover hover:scale-105 transition-transform duration-700"
              />
            </div>
          </div>

          <!-- Content -->
          <div v-animate="index % 2 === 0 ? 'animate-slide-left' : 'animate-fade-up'" class="w-full md:w-1/2 flex flex-col justify-center">
            <h3 class="text-3xl md:text-4xl font-bold text-white mb-6 leading-tight">
              {{ item.title }}
            </h3>
            
            <p class="text-lg text-slate-400 mb-8 leading-relaxed">
              {{ item.description }}
            </p>
            
            <ul v-if="item.features && item.features.length" class="space-y-5 mb-10">
              <li v-for="(feature, fIndex) in item.features" :key="fIndex" class="flex items-start gap-4">
                <div class="mt-1 flex-shrink-0 w-6 h-6 rounded-full bg-blue-500/10 flex items-center justify-center">
                  <svg class="w-4 h-4 text-blue-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="3">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7" />
                  </svg>
                </div>
                <span class="text-slate-300 text-lg">{{ feature }}</span>
              </li>
            </ul>

            <div v-if="item.link">
              <NuxtLink 
                :to="item.link"
                class="inline-flex items-center justify-center px-8 py-4 text-base font-semibold text-white bg-blue-600 rounded-xl hover:bg-blue-500 transition-colors duration-300 shadow-lg shadow-blue-900/20 group"
              >
                {{ item.linkLabel || 'Learn More' }}
                <svg class="w-5 h-5 ml-2 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M14 5l7 7m0 0l-7 7m7-7H3" />
                </svg>
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup lang="ts">
export interface GridItem {
  id?: string
  title: string
  description: string
  image: string
  features?: string[]
  link?: string
  linkLabel?: string
}

defineProps<{
  title?: string
  highlight?: string
  description?: string
  items: GridItem[]
}>()
</script>
