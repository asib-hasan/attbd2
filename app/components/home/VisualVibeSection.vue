<template>
  <section class="relative py-24 bg-slate-950 overflow-hidden">
    <div class="absolute inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-b from-slate-950 via-slate-900/90 to-slate-950"></div>
    </div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <!-- Text Content -->
        <div class="order-2 lg:order-1">
          <h2 class="text-4xl md:text-5xl font-black text-white leading-tight mb-6">
            Building the Infrastructure of <span class="text-accent-500">Tomorrow</span>.
          </h2>
          <p class="text-lg text-slate-300 mb-8 leading-relaxed">
            We don't just build roads and toll systems; we architect the arteries of modern commerce. Combining heavy civil engineering with cutting-edge digital operations, we deliver end-to-end solutions that drive nations forward.
          </p>
          
          <div class="flex gap-4">
            <NuxtLink to="/solutions" class="px-8 py-4 bg-white text-slate-950 font-bold rounded-full hover:bg-slate-200 transition-colors">
              Explore Our Work
            </NuxtLink>
          </div>
        </div>

        <!-- Image Composition -->
        <div class="order-1 lg:order-2 relative h-[500px] lg:h-[600px] w-full">
          <!-- Main Image -->
          <div class="absolute top-0 right-0 w-4/5 h-4/5 rounded-2xl overflow-hidden shadow-2xl border border-white/10 group">
            <div class="absolute inset-0 bg-slate-900/20 group-hover:bg-transparent transition-colors duration-500 z-10"></div>
            <img src="/More/3.png" alt="Infrastructure Tech" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700" />
          </div>
          
          <!-- Overlapping Image -->
          <div class="absolute bottom-0 left-0 w-3/5 h-3/5 rounded-2xl overflow-hidden shadow-2xl border-4 border-slate-950 group z-20">
            <div class="absolute inset-0 bg-slate-900/20 group-hover:bg-transparent transition-colors duration-500 z-10"></div>
            <img src="/More/1.jpg" alt="Civil Engineering" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700" />
          </div>
          
          <!-- Decorative element -->
          <div class="absolute top-1/2 -left-12 w-24 h-24 bg-accent-500/20 rounded-full blur-2xl z-0"></div>
          <div class="absolute bottom-12 right-12 w-32 h-32 bg-blue-500/20 rounded-full blur-3xl z-0"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Visual Vibe Component using the images from /More/
</script>
