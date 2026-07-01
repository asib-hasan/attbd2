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
    <div class="relative z-10 w-full h-full flex flex-col justify-end max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pb-32">
      <div class="max-w-5xl">
        <!-- Stark, immense typography -->
        <h1 class="text-6xl md:text-8xl lg:text-[7.5rem] font-black text-white leading-[0.95] tracking-tighter mb-8 animate-fade-in-up">
          Transforming<br />
          Nations.
        </h1>
        
        <div class="flex flex-col md:flex-row md:items-end justify-between gap-8 animate-fade-in-up delay-200">
          <p class="text-lg md:text-xl text-slate-300 leading-normal max-w-xl font-medium tracking-tight">
            From advanced electronic toll management to heavy civil construction. We build the vital systems that keep your world moving forward.
          </p>
          
          <div class="flex flex-wrap gap-4 shrink-0">
            <NuxtLink to="/solutions" class="px-8 py-4 bg-white text-black font-bold hover:bg-slate-200 transition-colors flex items-center gap-2 group text-sm uppercase tracking-widest">
              Discover Solutions
              <svg class="w-4 h-4 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
              </svg>
            </NuxtLink>
            <NuxtLink to="/contact" class="px-8 py-4 border border-white/30 text-white font-bold hover:bg-white hover:text-black transition-all flex items-center gap-2 text-sm uppercase tracking-widest">
              Get in Touch
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Professional, industry-standard minimalist hero section.
// Relies on high-quality video, stark typography, and strict spacing.
</script>

<style scoped>
.animate-fade-in-up {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 1s cubic-bezier(0.2, 0.8, 0.2, 1) forwards;
}

.delay-200 { animation-delay: 200ms; }

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
