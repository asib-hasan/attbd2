<template>
  <section class="py-24 bg-slate-950 relative z-20">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mb-20 text-center">
      <div v-animate="'animate-fade-up'" class="inline-flex items-center gap-2 px-4 py-2 bg-white/5 border border-white/10 rounded-full mb-6">
        <span class="w-2 h-2 rounded-full bg-accent-500"></span>
        <span class="text-slate-300 text-xs font-bold uppercase tracking-wider">Our Core Focus</span>
      </div>
      <h2 v-animate="'animate-fade-up delay-100'" class="text-4xl md:text-5xl font-black text-white">
        Driving Core Sectors Forward
      </h2>
    </div>

    <!-- Banner 1: Toll Management -->
    <div class="relative w-full h-[600px] lg:h-[700px] mb-8 overflow-hidden group">
      <div class="absolute inset-0">
        <img src="/slider/hero_toll_collection.png" alt="Toll Management" class="w-full h-full object-cover transform scale-105 group-hover:scale-110 transition-transform duration-[10s] ease-out" />
      </div>
      <!-- Dark gradient fading from left to right -->
      <div class="absolute inset-0 bg-gradient-to-r from-slate-950 via-slate-950/80 to-transparent"></div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-full flex items-center">
        <div class="max-w-2xl" v-animate="'animate-fade-up'">
          <div class="text-accent-500 font-bold tracking-widest uppercase mb-4 text-sm flex items-center gap-4">
            <span class="w-12 h-[1px] bg-accent-500"></span>
            Electronic Toll Collection
          </div>
          <h3 class="text-5xl lg:text-7xl font-black text-white mb-6 leading-tight">
            Seamless <br/>Highway Mobility
          </h3>
          <p class="text-xl text-slate-300 mb-10 leading-relaxed max-w-xl">
            We supply, install, and operate state-of-the-art Electronic Toll Collection (ETC) and Weigh-in-Motion systems to drastically reduce congestion and protect national infrastructure.
          </p>
          <NuxtLink to="/solutions" class="inline-flex items-center gap-3 px-8 py-4 bg-white/10 hover:bg-white/20 border border-white/20 backdrop-blur-md text-white font-bold rounded-full transition-all group/btn">
            Explore Toll Solutions
            <svg class="w-5 h-5 group-hover/btn:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
            </svg>
          </NuxtLink>
        </div>
      </div>
    </div>

    <!-- Banner 2: Civil Construction -->
    <div class="relative w-full h-[600px] lg:h-[700px] mb-8 overflow-hidden group">
      <div class="absolute inset-0">
        <img src="/slider/hero_traffic_system.png" alt="Civil Construction" class="w-full h-full object-cover transform scale-105 group-hover:scale-110 transition-transform duration-[10s] ease-out" />
      </div>
      <!-- Dark gradient fading from right to left -->
      <div class="absolute inset-0 bg-gradient-to-l from-slate-950 via-slate-950/80 to-transparent"></div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-full flex items-center justify-end text-right">
        <div class="max-w-2xl" v-animate="'animate-fade-up'">
          <div class="text-blue-500 font-bold tracking-widest uppercase mb-4 text-sm flex items-center justify-end gap-4">
            Heavy Engineering
            <span class="w-12 h-[1px] bg-blue-500"></span>
          </div>
          <h3 class="text-5xl lg:text-7xl font-black text-white mb-6 leading-tight">
            Building Massive <br/>Infrastructure
          </h3>
          <p class="text-xl text-slate-300 mb-10 leading-relaxed max-w-xl ml-auto">
            Executing major government projects. From bridges and highways to complex civil works, we are the trusted contractors for the nation's biggest developments.
          </p>
          <NuxtLink to="/services" class="inline-flex items-center gap-3 px-8 py-4 bg-white/10 hover:bg-white/20 border border-white/20 backdrop-blur-md text-white font-bold rounded-full transition-all group/btn">
            View Civil Projects
            <svg class="w-5 h-5 group-hover/btn:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
            </svg>
          </NuxtLink>
        </div>
      </div>
    </div>

    <!-- Banner 3: Shipbuilding -->
    <div class="relative w-full h-[600px] lg:h-[700px] overflow-hidden group">
      <div class="absolute inset-0">
        <!-- Using a placeholder image, update with an actual ship/port image if available -->
        <img src="/More/3.png" alt="Shipbuilding & Navigation" class="w-full h-full object-cover transform scale-105 group-hover:scale-110 transition-transform duration-[10s] ease-out" />
      </div>
      <!-- Dark gradient fading from left to right -->
      <div class="absolute inset-0 bg-gradient-to-r from-slate-950 via-slate-950/80 to-transparent"></div>
      
      <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-full flex items-center">
        <div class="max-w-2xl" v-animate="'animate-fade-up'">
          <div class="text-accent-500 font-bold tracking-widest uppercase mb-4 text-sm flex items-center gap-4">
            <span class="w-12 h-[1px] bg-accent-500"></span>
            Maritime & Navigation
          </div>
          <h3 class="text-5xl lg:text-7xl font-black text-white mb-6 leading-tight">
            Mastering the <br/>Waterways
          </h3>
          <p class="text-xl text-slate-300 mb-10 leading-relaxed max-w-xl">
            Through our sister concerns, we deliver comprehensive ship building, heavy carrier operations, and advanced maritime navigation solutions.
          </p>
          <NuxtLink to="/services" class="inline-flex items-center gap-3 px-8 py-4 bg-white/10 hover:bg-white/20 border border-white/20 backdrop-blur-md text-white font-bold rounded-full transition-all group/btn">
            Explore Maritime
            <svg class="w-5 h-5 group-hover/btn:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
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
