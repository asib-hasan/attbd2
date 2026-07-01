<template>
  <section class="relative h-screen min-h-[600px] max-h-[900px] overflow-hidden bg-slate-950">
    <!-- Video Background -->
    <div class="absolute inset-0 z-0 bg-slate-950">
      <video 
        autoplay 
        loop 
        muted 
        playsinline 
        class="absolute inset-0 w-full h-full object-cover"
      >
        <source src="/Video/video1.mp4" type="video/mp4" />
      </video>
      
      <!-- Dark Gradient Overlay to let the video shine through and provide contrast -->
      <div class="absolute inset-0 bg-gradient-to-r from-slate-950/90 via-slate-950/60 to-transparent pointer-events-none"></div>
      <div class="absolute inset-0 bg-gradient-to-t from-slate-950/80 via-transparent to-transparent pointer-events-none"></div>
    </div>

    <!-- Content -->
    <div class="relative z-10 w-full h-full flex flex-col justify-center max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pt-20">
      <div class="max-w-4xl">

        
        <h1 class="text-5xl md:text-7xl lg:text-8xl font-black text-white leading-[1.1] tracking-tight mb-8 animate-fade-up delay-100">
          Transforming<br />
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-cyan-300">
            Nations.
          </span>
        </h1>
        
        <p class="text-xl md:text-2xl text-slate-300 leading-relaxed max-w-2xl mb-12 animate-fade-up delay-200">
          From advanced electronic toll management to heavy civil construction. We build the systems that keep your world moving forward.
        </p>
        
        <div class="flex flex-wrap gap-4 animate-fade-up delay-300">
          <NuxtLink to="/solutions" class="px-8 py-4 bg-blue-600 text-white font-bold rounded-full hover:bg-blue-500 transition-colors shadow-lg shadow-blue-500/20 flex items-center gap-2">
            Discover Solutions
            <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
            </svg>
          </NuxtLink>
          <NuxtLink to="/contact" class="px-8 py-4 bg-white/10 backdrop-blur-sm border border-white/20 text-white font-bold rounded-full hover:bg-white/20 transition-all flex items-center gap-2">
            Get in Touch
          </NuxtLink>
        </div>
      </div>
    </div>
    

  </section>
</template>

<script setup lang="ts">
// Simplified Hero Section with Video Background for high-end aesthetic
</script>

<style scoped>
.animate-fade-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeUp 1s cubic-bezier(0.16, 1, 0.3, 1) forwards;
}

.delay-100 { animation-delay: 100ms; }
.delay-200 { animation-delay: 200ms; }
.delay-300 { animation-delay: 300ms; }

@keyframes fadeUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
