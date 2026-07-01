<template>
  <section class="py-24 bg-slate-50 relative z-20">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-20 text-center">
      <div v-animate="'animate-fade-up'" class="inline-flex items-center gap-2 px-4 py-2 bg-blue-50 border border-blue-100 rounded-full mb-6 shadow-sm">
        <span class="w-2 h-2 rounded-full bg-blue-600"></span>
        <span class="text-blue-700 text-xs font-bold uppercase tracking-wider">Our Core Focus</span>
      </div>
      <h2 v-animate="'animate-fade-up delay-100'" class="text-3xl md:text-4xl font-bold text-slate-900">
        Driving Core Sectors Forward
      </h2>
    </div>

    <!-- Banners Container -->
    <div class="w-full flex flex-col pb-24">
      
      <!-- Banner 1: Toll Management -->
      <div class="relative w-full h-[400px] lg:h-[450px] overflow-hidden group">
        <div class="absolute inset-0">
        <img src="/slider/bd_toll_plaza.png" alt="Electronic Toll Collection" class="w-full h-full object-cover transform scale-105 group-hover:scale-110 transition-transform duration-[10s] ease-out" />
      </div>
      <div class="absolute inset-0 bg-gradient-to-t from-slate-950/90 via-slate-900/10 to-transparent"></div>
      
      <div class="absolute bottom-0 left-0 w-full p-6 md:p-12 lg:p-16 z-10 flex flex-col md:flex-row md:items-end justify-between gap-6">
        <div class="max-w-3xl">
          <div class="text-blue-400 font-bold tracking-widest uppercase mb-3 text-xs flex items-center gap-4">
            <span class="w-12 h-[1px] bg-blue-400"></span>
            Electronic Toll Collection
          </div>
          <h3 class="text-2xl md:text-3xl lg:text-4xl font-bold text-white mb-2 leading-tight group-hover:-translate-y-2 transition-transform duration-500">
            Seamless Highway Mobility
          </h3>
          <div class="grid grid-rows-[0fr] group-hover:grid-rows-[1fr] transition-[grid-template-rows] duration-500 ease-in-out">
            <div class="overflow-hidden">
              <p class="text-base md:text-lg text-slate-300 pt-3 leading-relaxed max-w-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700 delay-100">
                We supply, install, and operate state-of-the-art Electronic Toll Collection (ETC) and Weigh-in-Motion systems to drastically reduce congestion and protect national infrastructure.
              </p>
            </div>
          </div>
        </div>
        
        <NuxtLink to="/solutions" class="inline-flex items-center justify-center gap-3 px-6 py-3 md:px-8 md:py-4 bg-white/10 backdrop-blur-md hover:bg-blue-600 border border-white/20 hover:border-transparent text-white font-bold rounded-full shadow-lg transition-all shrink-0">
          Explore Solutions
          <svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
          </svg>
        </NuxtLink>
      </div>
    </div>

      <!-- Banner 2: Civil Construction -->
      <div class="relative w-full h-[400px] lg:h-[450px] overflow-hidden group">
        <div class="absolute inset-0">
        <img src="/slider/bd_heavy_engineering.png" alt="Heavy Engineering" class="w-full h-full object-cover transform scale-105 group-hover:scale-110 transition-transform duration-[10s] ease-out" />
      </div>
      <div class="absolute inset-0 bg-gradient-to-t from-slate-950/90 via-slate-900/10 to-transparent"></div>
      
      <div class="absolute bottom-0 left-0 w-full p-6 md:p-12 lg:p-16 z-10 flex flex-col md:flex-row md:items-end justify-between gap-6">
        <div class="max-w-3xl">
          <div class="text-blue-400 font-bold tracking-widest uppercase mb-3 text-xs flex items-center gap-4">
            <span class="w-12 h-[1px] bg-blue-400"></span>
            Heavy Engineering
          </div>
          <h3 class="text-2xl md:text-3xl lg:text-4xl font-bold text-white mb-2 leading-tight group-hover:-translate-y-2 transition-transform duration-500">
            Building Massive Infrastructure
          </h3>
          <div class="grid grid-rows-[0fr] group-hover:grid-rows-[1fr] transition-[grid-template-rows] duration-500 ease-in-out">
            <div class="overflow-hidden">
              <p class="text-base md:text-lg text-slate-300 pt-3 leading-relaxed max-w-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700 delay-100">
                Executing major government projects. From bridges and highways to complex civil works, we are the trusted contractors for the nation's biggest developments.
              </p>
            </div>
          </div>
        </div>
        
        <NuxtLink to="/services" class="inline-flex items-center justify-center gap-3 px-6 py-3 md:px-8 md:py-4 bg-white/10 backdrop-blur-md hover:bg-blue-600 border border-white/20 hover:border-transparent text-white font-bold rounded-full shadow-lg transition-all shrink-0">
          View Projects
          <svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
          </svg>
        </NuxtLink>
      </div>
    </div>

      <!-- Banner 3: Maritime -->
      <div class="relative w-full h-[400px] lg:h-[450px] overflow-hidden group">
        <div class="absolute inset-0">
          <img src="/More/3.png" alt="Maritime & Navigation" class="w-full h-full object-cover transform scale-105 group-hover:scale-110 transition-transform duration-[10s] ease-out" />
        </div>
      <div class="absolute inset-0 bg-gradient-to-t from-slate-950/90 via-slate-900/10 to-transparent"></div>
      
      <div class="absolute bottom-0 left-0 w-full p-6 md:p-12 lg:p-16 z-10 flex flex-col md:flex-row md:items-end justify-between gap-6">
        <div class="max-w-3xl">
          <div class="text-blue-400 font-bold tracking-widest uppercase mb-3 text-xs flex items-center gap-4">
            <span class="w-12 h-[1px] bg-blue-400"></span>
            Maritime & Navigation
          </div>
          <h3 class="text-2xl md:text-3xl lg:text-4xl font-bold text-white mb-2 leading-tight group-hover:-translate-y-2 transition-transform duration-500">
            Mastering the Waterways
          </h3>
          <div class="grid grid-rows-[0fr] group-hover:grid-rows-[1fr] transition-[grid-template-rows] duration-500 ease-in-out">
            <div class="overflow-hidden">
              <p class="text-base md:text-lg text-slate-300 pt-3 leading-relaxed max-w-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-700 delay-100">
                Through our sister concerns, we deliver comprehensive ship building, heavy carrier operations, and advanced maritime navigation solutions.
              </p>
            </div>
          </div>
        </div>
        
        <NuxtLink to="/services" class="inline-flex items-center justify-center gap-3 px-6 py-3 md:px-8 md:py-4 bg-white/10 backdrop-blur-md hover:bg-blue-600 border border-white/20 hover:border-transparent text-white font-bold rounded-full shadow-lg transition-all shrink-0">
          Explore Maritime
          <svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
            <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
          </svg>
        </NuxtLink>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup lang="ts">
// Full-width banner highlight section for Tolls, Construction, and Shipbuilding
</script>
