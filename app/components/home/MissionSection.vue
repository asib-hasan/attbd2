<template>
  <!-- Mission Section -->
  <section class="py-24 bg-slate-950 relative z-20 border-t border-white/5">
    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="bg-slate-900/50 backdrop-blur-xl rounded-[40px] border border-white/10 p-8 lg:p-16 relative overflow-hidden">
        <!-- Background Blur -->
        <div class="absolute top-0 right-0 w-80 h-80 bg-accent-500/10 rounded-full blur-3xl pointer-events-none"></div>
        <div class="absolute bottom-0 left-0 w-80 h-80 bg-blue-500/10 rounded-full blur-3xl pointer-events-none"></div>
        
        <div class="grid lg:grid-cols-2 gap-16 items-center relative z-10">
        <div>
          <div v-animate="'animate-fade-up'" class="inline-flex items-center gap-2 mb-4 px-3 py-1.5 bg-white/5 border border-white/10 rounded-full">
            <span class="w-2 h-2 rounded-full bg-accent-500"></span>
            <span class="text-slate-300 text-xs font-bold uppercase tracking-wider">Our Purpose</span>
          </div>
          <h2 v-animate="'animate-fade-up delay-100'" class="text-4xl md:text-5xl font-black text-white mb-6 leading-tight">
            Leading Bangladesh's<br/>
            <span class="text-transparent bg-clip-text bg-gradient-to-r from-accent-400 to-blue-400">Transportation Future</span>
          </h2>
          <p v-animate="'animate-fade-up delay-200'" class="text-slate-400 text-lg leading-relaxed mb-6">
            To hold the leadership in Bangladesh by means of continuous strive in offering quality management for Operation & Maintenance of ETC of Roads & Highways.
          </p>
          <p v-animate="'animate-fade-up delay-300'" class="text-slate-400 text-lg leading-relaxed mb-8">
            To become the market leader for Highways Systems Technology development in Bangladesh, leveraging cutting-edge ITS technologies.
          </p>
          <div v-animate="'animate-fade-up delay-400'">
            <NuxtLink to="/about" class="inline-flex items-center gap-2 text-white font-semibold hover:gap-3 transition-all duration-300 group">
              <span class="border-b border-white/30 pb-0.5 group-hover:border-white">Learn more about ATT</span>
              <svg class="w-5 h-5 text-accent-500" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"/></svg>
            </NuxtLink>
          </div>
        </div>

        <!-- Right: Mission/Vision cards -->
        <div class="grid grid-cols-1 gap-8">
          <div v-for="(card, index) in cards" :key="card.title" v-animate="`animate-fade-up delay-${(index + 2) * 100}`" class="bg-slate-950/80 backdrop-blur-md rounded-2xl p-8 group hover:bg-slate-900 transition-colors duration-300 relative z-10 border border-white/5">
            <!-- Icon pop -->
            <div class="absolute -top-6 -left-6 w-16 h-16 bg-slate-800 rounded-full flex items-center justify-center shadow-2xl border border-white/10 group-hover:scale-110 group-hover:bg-accent-500 transition-all duration-300">
              <svg v-if="index === 0" class="w-8 h-8 text-accent-500 group-hover:text-slate-900 transition-colors" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 13.5l10.5-11.25L12 10.5h8.25L9.75 21.75 12 13.5H3.75z" />
              </svg>
              <svg v-else class="w-8 h-8 text-blue-400 group-hover:text-slate-900 transition-colors" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                <path stroke-linecap="round" stroke-linejoin="round" d="M2.036 12.322a1.012 1.012 0 010-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
            </div>
            
            <div class="ml-6">
              <h3 class="text-white font-black text-2xl uppercase tracking-wide mb-3 flex items-center gap-3">
                <span class="w-1 h-6 bg-accent-500"></span>
                {{ card.title }}
              </h3>
              <p class="text-slate-400 leading-relaxed text-lg">{{ card.text }}</p>
            </div>
          </div>
        </div>
      </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const cards = [
  {
    title: 'Our Mission',
    text: 'Continuous quality improvement in the operation and maintenance of Electronic Toll Collection systems for Roads & Highways across Bangladesh.',
  },
  {
    title: 'Our Vision',
    text: 'To become the undisputed market leader for Highways Systems Technology development in Bangladesh, setting regional standards for ITS excellence.',
  },
]
</script>
