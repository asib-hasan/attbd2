<template>
  <section class="py-24 bg-white relative">
    <div class="text-center mb-16">
      <h2 v-animate="'animate-fade-up'" class="text-3xl md:text-4xl font-bold text-[#0B2046]">
        Some Of Our Work
      </h2>
    </div>

    <!-- Full width container, grid of 3 with no gaps -->
    <div class="w-full grid grid-cols-1 md:grid-cols-3 gap-0">
      
      <!-- Work Item 1 -->
      <div class="relative w-full h-[400px] md:h-[500px] overflow-hidden group cursor-pointer">
        <!-- Make sure image has transition for hover effect -->
        <img src="/slider/bd_toll_plaza.png" alt="Toll Plaza" class="w-full h-full object-cover transform scale-100 group-hover:scale-110 transition-transform duration-[800ms] ease-out" />
        
        <!-- Hover Overlay -->
        <div class="absolute bottom-0 left-0 w-full bg-white/90 backdrop-blur-md transform translate-y-full group-hover:translate-y-0 transition-transform duration-500 ease-out flex justify-between items-stretch">
          <div class="p-6">
            <h4 class="text-xl font-bold text-slate-900 mb-1">Modern Toll Collection</h4>
            <p class="text-slate-500 text-sm">Infrastructure</p>
          </div>
          <!-- Blue Square Button -->
          <div class="bg-blue-600 group-hover:bg-[#0B2046] text-white w-16 flex items-center justify-center transition-colors duration-300 shrink-0">
            <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 4v16m8-8H4" />
            </svg>
          </div>
        </div>
      </div>

      <!-- Work Item 2 -->
      <div class="relative w-full h-[400px] md:h-[500px] overflow-hidden group cursor-pointer">
        <img src="/slider/bd_heavy_engineering.png" alt="Heavy Engineering" class="w-full h-full object-cover transform scale-100 group-hover:scale-110 transition-transform duration-[800ms] ease-out" />
        
        <!-- Hover Overlay -->
        <div class="absolute bottom-0 left-0 w-full bg-white/90 backdrop-blur-md transform translate-y-full group-hover:translate-y-0 transition-transform duration-500 ease-out flex justify-between items-stretch">
          <div class="p-6">
            <h4 class="text-xl font-bold text-slate-900 mb-1">Bridge Construction</h4>
            <p class="text-slate-500 text-sm">Civil Engineering</p>
          </div>
          <div class="bg-blue-600 group-hover:bg-[#0B2046] text-white w-16 flex items-center justify-center transition-colors duration-300 shrink-0">
            <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 4v16m8-8H4" />
            </svg>
          </div>
        </div>
      </div>

      <!-- Work Item 3 -->
      <div class="relative w-full h-[400px] md:h-[500px] overflow-hidden group cursor-pointer">
        <img src="/slider/bd_maritime.png" alt="Maritime Navigation" class="w-full h-full object-cover transform scale-100 group-hover:scale-110 transition-transform duration-[800ms] ease-out" />
        
        <!-- Hover Overlay -->
        <div class="absolute bottom-0 left-0 w-full bg-white/90 backdrop-blur-md transform translate-y-full group-hover:translate-y-0 transition-transform duration-500 ease-out flex justify-between items-stretch">
          <div class="p-6">
            <h4 class="text-xl font-bold text-slate-900 mb-1">Shipbuilding Yard</h4>
            <p class="text-slate-500 text-sm">Maritime</p>
          </div>
          <div class="bg-blue-600 group-hover:bg-[#0B2046] text-white w-16 flex items-center justify-center transition-colors duration-300 shrink-0">
            <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M12 4v16m8-8H4" />
            </svg>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup lang="ts">
// Our Work section mimicking the CodeIt template portfolio layout
</script>
