<template>
  <NuxtLink :to="link" class="group flex flex-col bg-white border border-slate-200 hover:border-blue-200 hover:shadow-xl hover:shadow-blue-900/5 transition-all duration-500 rounded-3xl relative overflow-hidden h-full">
    
    <!-- Image Area -->
    <div class="h-64 sm:h-72 bg-slate-100 overflow-hidden relative border-b border-slate-100">
      <img :src="image" :alt="title" class="w-full h-full object-cover relative z-10 group-hover:scale-110 transition-transform duration-700 ease-out" />
      <div class="absolute inset-0 bg-gradient-to-t from-slate-900/10 to-transparent z-20 pointer-events-none"></div>
    </div>

    <!-- Content Area -->
    <div class="p-8 flex flex-col flex-grow bg-white relative">
      <h3 class="text-xl font-bold text-slate-900 uppercase tracking-tight mb-4 leading-tight group-hover:text-blue-600 transition-colors">
        {{ title }}
      </h3>
      <p class="text-slate-600 text-sm leading-relaxed mb-6 flex-grow">
        {{ description }}
      </p>

      <!-- Specifications Snippet -->
      <ul class="space-y-3 mb-8" v-if="specs && specs.length">
        <li v-for="(spec, idx) in specs.slice(0, 2)" :key="idx" class="flex items-start gap-3 text-sm text-slate-700 font-medium">
          <svg class="w-4 h-4 text-blue-600 flex-shrink-0 mt-0.5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M5 13l4 4L19 7"/></svg>
          <span class="leading-relaxed">{{ spec }}</span>
        </li>
      </ul>

      <!-- CTA -->
      <div class="mt-auto flex items-center gap-3 text-xs font-bold text-slate-500 group-hover:text-blue-600 transition-colors uppercase tracking-widest pt-5 border-t border-slate-100">
        View Specs
        <svg class="w-4 h-4 group-hover:translate-x-1.5 transition-transform duration-300" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
      </div>

      <!-- Standard Animated Bottom Border Line -->
      <div class="absolute bottom-0 left-0 h-[6px] bg-blue-600 w-0 group-hover:w-full transition-all duration-500 ease-out z-20"></div>
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
