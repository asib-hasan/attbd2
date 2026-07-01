<template>
  <section class="relative py-20 md:py-24 overflow-hidden flex flex-col items-center justify-center text-center">
    
    <!-- Background Image -->
    <div v-if="bgImage" class="absolute inset-0 z-0 overflow-hidden bg-slate-900">
      <!-- Full color, native image just slightly darkened for text readability -->
      <img :src="bgImage" alt="Background" class="w-full h-full object-cover scale-105 opacity-70" />
      
      <!-- Neutral dark overlay (no colors) to ensure white text is readable -->
      <div class="absolute inset-0 bg-black/60"></div>
    </div>
    
    <!-- Fallback if no image is provided -->
    <div v-else class="absolute inset-0 z-0 overflow-hidden bg-[#0B2046]"></div>

    <!-- Centered Content -->
    <div class="relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center">
      <!-- Minimalist Title -->
      <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold tracking-tight text-white mb-4 drop-shadow-md">
        {{ title }}
      </h1>
      
      <!-- Optional Subtitle -->
      <p v-if="subtitle" class="text-base md:text-lg max-w-3xl leading-relaxed text-slate-200 font-medium drop-shadow-md">
        {{ subtitle }}
      </p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  subtitle?: string
  bgImage?: string
}>()
</script>

<style scoped>
</style>
