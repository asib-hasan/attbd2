<template>
  <section class="relative py-24 bg-white overflow-hidden">
    <div class="absolute inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-b from-white via-slate-50/90 to-white"></div>
    </div>
    
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
        <!-- Text Content -->
        <div class="order-2 lg:order-1">
          <h2 class="text-3xl md:text-4xl font-bold text-slate-900 leading-tight mb-6">
            Building the Infrastructure of <span class="text-blue-600">Tomorrow</span>.
          </h2>
          <p class="text-lg text-slate-600 mb-8 leading-relaxed">
            We don't just build roads and toll systems; we architect the arteries of modern commerce. Combining heavy civil engineering with cutting-edge digital operations, we deliver end-to-end solutions that drive nations forward.
          </p>
          
          <div class="flex gap-4">
            <NuxtLink to="/solutions" class="px-8 py-4 bg-blue-600 text-white font-bold rounded-md shadow-md hover:bg-blue-700 transition-colors">
              Explore Our Work
            </NuxtLink>
          </div>
        </div>

        <!-- Image Composition -->
        <div class="order-1 lg:order-2 relative h-[500px] lg:h-[600px] w-full">
          <!-- Main Image -->
          <div class="absolute top-0 right-0 w-4/5 h-4/5 rounded-2xl overflow-hidden shadow-2xl border border-slate-100 group">
            <div class="absolute inset-0 bg-white/10 group-hover:bg-transparent transition-colors duration-500 z-10"></div>
            <img src="/More/3.png" alt="Infrastructure Tech" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700" />
          </div>
          
          <!-- Overlapping Image -->
          <div class="absolute bottom-0 left-0 w-3/5 h-3/5 rounded-2xl overflow-hidden shadow-2xl border-4 border-white group z-20">
            <div class="absolute inset-0 bg-white/10 group-hover:bg-transparent transition-colors duration-500 z-10"></div>
            <img src="/More/1.jpg" alt="Civil Engineering" class="w-full h-full object-cover transform group-hover:scale-105 transition-transform duration-700" />
          </div>
          
          <!-- Decorative element -->
          <div class="absolute top-1/2 -left-12 w-24 h-24 bg-blue-500/10 rounded-full blur-2xl z-0"></div>
          <div class="absolute bottom-12 right-12 w-32 h-32 bg-cyan-500/10 rounded-full blur-3xl z-0"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Visual Vibe Component using the images from /More/
</script>
