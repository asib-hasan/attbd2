<template>
  <section class="relative bg-slate-950 pt-32 pb-24 md:pt-40 md:pb-32 overflow-hidden flex flex-col items-center justify-center text-center">
    <!-- Background Image or Pattern -->
    <div v-if="bgImage" class="absolute inset-0 z-0 overflow-hidden">
      <!-- Added grayscale and lowered opacity to match the moody dark feel -->
      <img :src="bgImage" alt="Background" class="w-full h-full object-cover opacity-20 grayscale scale-105" />
      <div class="absolute inset-0 bg-slate-950/80"></div>
    </div>
    <div v-else class="absolute inset-0 z-0 bg-slate-950 overflow-hidden">
      <!-- Dark backdrop to mimic the screenshot -->
      <div class="absolute inset-0 bg-slate-950"></div>
    </div>

    <!-- Clean, Centered Content -->
    <div class="relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center">
      <!-- Minimalist Title -->
      <h1 class="text-5xl md:text-6xl lg:text-[80px] font-black text-white tracking-tight leading-none drop-shadow-2xl">
        {{ title }}
      </h1>
      
      <!-- Optional Subtitle -->
      <p v-if="subtitle" class="text-base md:text-xl text-slate-400 max-w-3xl leading-relaxed mt-6">
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
/* No extra animations needed to match the extremely clean look from the screenshot */
</style>
