<template>
  <section class="relative h-screen min-h-[700px] overflow-hidden bg-black">
    <!-- Video Background -->
    <div class="absolute inset-0 z-0">
      <video 
        autoplay 
        loop 
        muted 
        playsinline 
        class="absolute inset-0 w-full h-full object-cover opacity-60"
      >
        <source src="/Video/video1.mp4" type="video/mp4" />
      </video>
      
      <!-- Minimal Vignette Overlay -->
      <div class="absolute inset-0 bg-gradient-to-t from-black via-black/20 to-black/40"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 w-full h-full flex flex-col justify-center items-center text-center max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="max-w-4xl mx-auto flex flex-col items-center">
        
        <!-- Refined Typography -->
        <h1 class="text-5xl md:text-6xl lg:text-7xl font-extrabold text-transparent bg-clip-text bg-gradient-to-b from-white via-white to-white/60 leading-[1.1] tracking-tight mb-6 animate-fade-in-up delay-100">
          ASIAN TRAFFIC TECHNOLOGIES
        </h1>
        
        <p class="text-lg md:text-xl text-slate-300/90 leading-relaxed max-w-2xl font-light mb-10 animate-fade-in-up delay-200">
          From advanced electronic toll management to heavy civil construction, we engineer the vital infrastructure that propels your world forward.
        </p>
        
        <!-- Polished Buttons -->
        <div class="flex flex-col sm:flex-row items-center gap-4 w-full sm:w-auto animate-fade-in-up delay-300">
          <NuxtLink to="/solutions" class="w-full sm:w-auto px-8 py-4 bg-white text-black font-semibold rounded-full hover:bg-slate-100 hover:scale-105 transition-all duration-300 flex items-center justify-center gap-2 group shadow-[0_0_20px_rgba(255,255,255,0.15)]">
            Discover Solutions
            <svg class="w-4 h-4 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
            </svg>
          </NuxtLink>
          <NuxtLink to="/contact" class="w-full sm:w-auto px-8 py-4 border border-white/20 rounded-full text-white font-semibold hover:bg-white/10 hover:border-white/40 backdrop-blur-sm transition-all duration-300 flex items-center justify-center gap-2">
            Get in Touch
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Professional, industry-standard modern hero section.
// Features elegant typography, smooth animations, and premium glassmorphism elements.
</script>

<style scoped>
.animate-fade-in-up {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 1s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
}

.delay-100 { animation-delay: 100ms; }
.delay-200 { animation-delay: 200ms; }
.delay-300 { animation-delay: 300ms; }

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
