<template>
  <div>
    <PageHero
      title="Our Solutions"
      subtitle="Intelligent Transportation Systems tailored for Bangladesh's roads, bridges, ports and infrastructure — from concept through to long-term maintenance."
      bgImage="/slider/new_toll_plaza.png"
    />

    <!-- Animated Industry Specializations Section -->
    <section class="py-24 bg-slate-50 overflow-hidden relative border-t border-slate-200">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-16 text-center">
        <div class="text-[10px] font-bold text-blue-600 uppercase tracking-widest mb-3">Serving Industries</div>
        <h2 class="text-3xl md:text-5xl font-black text-slate-900 tracking-tight">Industry Specializations</h2>
      </div>

      <div class="relative w-full flex flex-col gap-6 py-4">
        <!-- Row 1: Left -->
        <div class="flex whitespace-nowrap animate-marquee-left hover:pause-animation w-max">
          <div v-for="i in 3" :key="`r1-${i}`" class="flex gap-6 pr-6">
            <span v-for="industry in row1" :key="industry" class="px-8 py-4 bg-white rounded-full text-slate-900 font-bold shadow-sm border border-slate-100 text-lg flex items-center justify-center min-w-[200px]">
              {{ industry }}
            </span>
          </div>
        </div>

        <!-- Row 2: Right -->
        <div class="flex whitespace-nowrap animate-marquee-right hover:pause-animation w-max">
          <div v-for="i in 3" :key="`r2-${i}`" class="flex gap-6 pr-6">
            <span v-for="industry in row2" :key="industry" class="px-8 py-4 bg-white rounded-full text-slate-900 font-bold shadow-sm border border-slate-100 text-lg flex items-center justify-center min-w-[200px]">
              {{ industry }}
            </span>
          </div>
        </div>

        <!-- Row 3: Left -->
        <div class="flex whitespace-nowrap animate-marquee-left-fast hover:pause-animation w-max">
          <div v-for="i in 3" :key="`r3-${i}`" class="flex gap-6 pr-6">
            <span v-for="industry in row3" :key="industry" class="px-8 py-4 bg-white rounded-full text-slate-900 font-bold shadow-sm border border-slate-100 text-lg flex items-center justify-center min-w-[200px]">
              {{ industry }}
            </span>
          </div>
        </div>
        
        <!-- Fading Edges for smooth look -->
        <div class="absolute inset-y-0 left-0 w-32 bg-gradient-to-r from-slate-50 to-transparent z-10 pointer-events-none"></div>
        <div class="absolute inset-y-0 right-0 w-32 bg-gradient-to-l from-slate-50 to-transparent z-10 pointer-events-none"></div>
      </div>
    </section>

    <AlternatingGrid 
      title="Our Solutions" 
      highlight="Explore" 
      description="We offer end-to-end ITS solutions, from toll management to ship building and weighing infrastructure."
      :items="formattedSolutions" 
    />


  </div>
</template>

<style scoped>
.animate-marquee-left {
  animation: marquee-left 40s linear infinite;
}
.animate-marquee-right {
  animation: marquee-right 45s linear infinite;
}
.animate-marquee-left-fast {
  animation: marquee-left 35s linear infinite;
}
.hover\:pause-animation:hover {
  animation-play-state: paused;
}

@keyframes marquee-left {
  0% { transform: translateX(0); }
  100% { transform: translateX(-33.33%); }
}

@keyframes marquee-right {
  0% { transform: translateX(-33.333%); }
  100% { transform: translateX(0); }
}
</style>

<script setup lang="ts">
import { computed } from 'vue'
import { solutions } from '~/data/solutions'

useSeoMeta({
  title: 'Solutions — ATT | Intelligent Transportation Systems Bangladesh',
  description: 'Explore ATT\'s complete range of ITS solutions: toll collection, security, traffic monitoring, bridge safety, HTMS, customized software and more.',
})

const row1 = ['Technology', 'Non-profit', 'Healthcare', 'Real Estate', 'Logistics', 'Maritime']
const row2 = ['E-commerce', 'Professional Services', 'Technology', 'Non-profit', 'Civil Engineering', 'Government']
const row3 = ['Healthcare', 'Non-profit', 'Real Estate', 'E-commerce', 'Transportation', 'Manufacturing']

const formattedSolutions = computed(() => {
  return solutions.map((s, index) => {
    // Provide a default image based on index if none exists
    const defaultImages = [
      '/slider/photorealistic_toll_system.png',
      '/projects/2.png',
      '/projects/3.png',
      '/projects/4.png',
      '/projects/5.png',
    ]
    const imgUrl = s.image || defaultImages[index % defaultImages.length]

    return {
      id: s.slug,
      title: s.title,
      description: s.description || s.shortDesc,
      image: imgUrl,
      features: s.features || (s as any).achievements || [],
    }
  })
})
</script>
