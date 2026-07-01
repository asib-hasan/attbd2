<template>
  <NuxtLink :to="link" class="group flex flex-col bg-slate-900 border border-white/5 hover:border-accent-500 hover:shadow-[0_0_30px_rgba(59,130,246,0.1)] transition-all duration-500 rounded-3xl relative overflow-hidden h-full">
    <!-- Top accent line -->
    <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-accent-500 to-blue-500 transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left duration-500 z-10"></div>
    
    <!-- Image Area -->
    <div class="h-64 bg-slate-950/50 flex items-center justify-center p-8 overflow-hidden relative border-b border-white/5">
      <div class="absolute inset-0 bg-slate-900/40 group-hover:bg-transparent transition-colors duration-500 z-0"></div>
      <!-- Invert filter conditionally applied if product images are mostly dark/black logos. Adjust if they are full-color photos. -->
      <img :src="image" :alt="title" class="w-full h-full object-contain relative z-10 group-hover:scale-110 transition-transform duration-700 ease-out drop-shadow-2xl" />
    </div>

    <!-- Content Area -->
    <div class="p-8 flex flex-col flex-grow">
      <h3 class="text-xl font-black text-white uppercase tracking-tight mb-4 leading-tight group-hover:text-accent-400 transition-colors">
        {{ title }}
      </h3>
      <p class="text-slate-400 text-sm leading-relaxed mb-6 flex-grow">
        {{ description }}
      </p>

      <!-- Specifications Snippet -->
      <ul class="space-y-3 mb-8" v-if="specs && specs.length">
        <li v-for="(spec, idx) in specs.slice(0, 2)" :key="idx" class="flex items-start gap-3 text-xs text-slate-300 font-medium">
          <svg class="w-4 h-4 text-accent-500 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span class="leading-relaxed">{{ spec }}</span>
        </li>
      </ul>

      <!-- CTA -->
      <div class="mt-auto flex items-center gap-3 text-xs font-bold text-slate-300 group-hover:text-accent-400 transition-colors uppercase tracking-widest pt-4 border-t border-white/5">
        View Specs
        <svg class="w-4 h-4 group-hover:translate-x-1.5 transition-transform duration-300" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
      </div>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  description: string
  image: string
  specs?: string[]
  link: string
}>()
</script>
